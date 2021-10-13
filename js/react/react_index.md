# React

## List of contents

- [Django](#django)
  - [List of contents](#list-of-contents)
    - [Swagger documentation for django drf project](#swagger-documentation-for-django-drf-project)

---

### Extending EventLisiners from input to other components

#### Tags

> javascript
> react
> js
> eventlisener

see on [stackoverflow](https://stackoverflow.com/a/44434971)

```js
<Form noValidate
    onSubmit={(e) => {
        e.preventDefault();
        console.log(errors, errorsToDisplay)
        setErrorsToDisplay(errors)
        // useForceUpdate()
        return handleSubmit(e)
    }}
    onKeyDownCapture={(e) => { formHotkey(e, {barcodeStart, setBarcodeStart}, {barcodeBuff, setBarcodeBuff})
        updateCodeInForm(barcodeBuff, values)
    }}
    tabIndex={0}
>
```

---
