---
title: "Hook creation"
date: 2019-02-18T19:57:39+01:00
weight: 4
---

### Hook creation

**Reacli** also enables to create React hooks. The functioning is quite similar to components creation. To create a hook with the default configuration:

```bash
reacli hook ./my-super-hook
```

It will generate a structure like:

```text
.
└── my-super-hook
    ├── hooks
    |   ├── MySuperHook.jsx
    |   └── MySuperHook.css
    └── index.js
```

#### Options

You can configure some options to customize the way **Reacli** creates your hook:

- `--scss` to use a SCSS style file instead of the default CSS one
- `--extension [value]` where `value` is either "*js*" or "*jsx*" to configure the file extension of the generated hook files
- `-i` or `--ignore-config-file` to ignore the `.reacli` configuration file if one is found and use default options or the ones given at runtime to the CLI

##### Create several hooks at once

To create several hooks in one single command, just type several paths such as:

```bash
reacli hook ./my-super-hook1 ./my-super-hook2
```

{{% notice tip %}}
If you use [options]({{< relref "options/_index.md" >}}) in the CLI or have a [configuration file]({{< relref "options/configFile.md" >}}), those parameters will be applied to the generated hooks.
{{% /notice %}}