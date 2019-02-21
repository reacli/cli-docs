---
title: "Flow"
date: 2019-02-18T19:44:08+01:00
weight: 3
---

Some users might want to type their components with [`flow`](https://flow.org/).

To create a `flow`-typed component, just use **Reacli** with either the `--flow` or the `-f` option:

```bash
reacli component ./my-super-component -f
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

![flow-container-component](/options/images/flow-container-component.png?width=70%)

### Explanation

- First, we set the `// @flow` annotation to configure the component to be `flow`-typed
- We create `Props` and `State` types, in which we will type our component props or type. 
- Then, we pass those types to the generic `Component` class.
- We also create a static object called `defaultProps` in which we will be able to add some values to the component props that are not required.

## Dumb component

### Generated component 

![flow-dumb-component](/options/images/flow-dumb-component.png?width=70%)

### Explanation

- Here again, we set the `// @flow` annotation to configure the component to be `flow`-typed
- We then configure the `Props` type to contain one optional prop called `value1` of type `string`
- The dumb component is a functional one, and we type its input as being of the `Props` type
- Finally, we set the `defaultProps` to configure the default values for the props that are not required (an empty string for the `value1` prop)