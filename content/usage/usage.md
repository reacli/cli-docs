---
title: "Use Reacli"
date: 2019-02-18T19:57:39+01:00
weight: 1
---

### Basic usage

#### If **Reacli** is installed globally

Once you have **Reacli** globally installed (see [installation]({{< relref "install.md" >}})), you can directly use it like this:

```bash
reacli component path/to/my/component
```

#### If you did not install **Reacli**

You don't need to have **Reacli** installed globally to use it. You can use `npx` to run it wherever you want:

```bash
npx reacli component path/to/my/component
```

### Advanced usage

#### Create several components at once

You can create several components at once by running the following command:

```bash
reacli component ./my-super-comp1 ./my-super-comp2
```

**Reacli** will then generate several components.

{{% notice tip %}}
If you use [options]({{< relref "options/_index.md" >}}) in the CLI or have a [configuration file]({{< relref "options/configFile.md" >}}), those parameters will be applied to the generated components.
{{% /notice %}}
