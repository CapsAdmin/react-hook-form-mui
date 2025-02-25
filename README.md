# Material-UI and react-hook-form combined

## About this project

This project simplifies the use of `react-hook-form` and `Material-UI`. It provides opinionated use cases with following
components:

* FormContainer
* TextFieldElement
* SelectElement
* MultiSelectElement
* RadioButtonGroup
* CheckboxButtonGroup
* CheckboxElement
* SwitchElement
* PasswordElement
* DatePickerElement

The components are written in TypeScript and attempt an easy integration.

## How to use it

### Installation

```console
npm install react-hook-form react-hook-form-mui
```

The dependency of `react-hook-form` is a peerDependency so don't forget to install it as well.

### Important

From versions >= 3.x of this package MUI v5 is in use. Versions of 1 & 2 using Material-UI v4

### Your component code

```tsx
import { FormContainer, TextFieldElement } from 'react-hook-form-mui'

function Form() {
  return (
    <FormContainer 
      defaultValues={{ name: '' }}
      onSuccess={data => console.log(data)}
    >
      <TextFieldElement name="name" label="Name" required />
    </FormContainer>
  )
}
```

You can have a look at the `example` folder which sets up NextJS with `react-hook-form-mui`

### FormContainer creates `formContext`

The `<FormContainer />` wires up a form and you can create sub-components which either make use
of `useFormContext() | useWatch()` to react to form values.

## Demo

Check out Storybook: [Demo](https://react-hook-form-material-ui.vercel.app)

You will find examples and use cases.

### With Datepicker

If you are using the `DatepickerElement` keep in mind that you have to wrap your form with a provider:

Examples for Dayjs or DateFns provider (used in the demo):

* [DateFns](/src/DateFnsProvider.tsx)
* [Dayjs](/src/DateFnsProvider.tsx)

### Bundle

This project uses `microbundle` to wrap the package for `npm`.

### License

[MIT](./LICENSE)

### Backlog history

* 3.3.0 Fix `FormContainer` `children` prop on React 18 typing changes. Kudos to @TimMikeladze
* 3.2.0 New props `showCheckbox` on MultiSelect field and minor improvements.
* 3.1.5 Update dependencies and fix peer
* 3.1.4 Improve error color on checkbox
* 3.1 Add SwitchElement component
* 3.x Material v5. Change components to use `@mui/material`
* 2.1.x Introduce prop `row` to CheckboxButtonGroup and RadioButtonGroup
* 2.x Rename package to react-hook-form-mui
* 1.x Deprecated

