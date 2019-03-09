---
title: "Component creation"
date: 2019-02-18T19:57:39+01:00
weight: 3
---

### Component creation

**Reacli**'s main feature is to create easily new components. To create a new component with the default configuration:

```
reacli component ./my-super-component
```

It will generate a structure like:

```text
.
└── my-super-component
    ├── components
    |   ├── MySuperComponent.jsx
    |   ├── MySuperComponent.css
    |   └── MySuperComponentContainer.jsx
    └── index.js
```

#### Options

**Reacli** enables to customize your components creation thanks to several options. You can combine several options.

- `-f` or `--flow` option adds Flow to your generated component
- `--scss` to use a SCSS style file instead of the default CSS one
- `--redux` option adds a React-Redux default configuration to your generated component
- `-i` or `--ignore-config-file` to ignore the `.reacli` configuration file if one is found and use default options or the ones given at runtime to the CLI
- `--extension [value]` where `value` is either "*js*" or "*jsx*" to configure the file extension of the generated component files

##### Create several components at once

To create several components in one single command, just type several paths such as:

```bash
reacli component ./my-super-component1 ./my-super-component2
```

{{% notice tip %}}
If you use [options]({{< relref "options/_index.md" >}}) in the CLI or have a [configuration file]({{< relref "options/configFile.md" >}}), those parameters will be applied to the generated components.
{{% /notice %}}