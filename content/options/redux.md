---
title: "Redux"
date: 2019-02-18T19:44:08+01:00
weight: 4
---

## Explanation

Some users might want to use [React Redux](https://react-redux.js.org/) to share props accross components that are at different levels of the DOM.

_Redux_ needs _actions_ to be dispatched in components. Those actions will then be reduced by _reducers_.

## Usage

You can generate a component connected to the _Redux_ `store` using the following command: 
```bash
reacli component ./my-super-component --redux
```

It will generate a structure like this:
```text
    .
    └── my-super-component
        ├── components
        |   ├── MySuperComponent.jsx
        |   ├── MySuperComponent.css
        |   └── MySuperComponentContainer.jsx
        └── index.js
```

## Container component

### Generated component 

It will only have an impact on the container component, which will look like the following:

![redux-container-component](/options/images/redux-container-component.png?width=70%)


### Explanation

- First, the `connect` method is imported from `react-redux`. It will enable the generated component to interact with the _Redux_ `store`
- We then define a `mapStateToProps` method. In this arrow function (which can take a `state` variable as input), we will be able to create component props from variables stored in the _Redux_ `store`
- The `mapDispatchToProps` method is optional. It will be used if your component has to dispatch actions
- Finally, we need to bind our component with the _Redux_ `store` using the previously imported `connect` method

{{% notice info %}}
If your component does **not have to dispatch actions**, you can delete the **`mapDispatchToProps`** function.
In that case, do not forget to also remove it from the **`connect()`** call. 
{{% /notice %}}