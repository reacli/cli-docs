---
title: "Configuration file"
date: 2019-02-18T19:44:08+01:00
weight: 6
---

## Description 

Some users might want to use the _Reacli_ CLI to create several components in the same project. Each component might have to be configured with the same options. 

{{% notice tip %}}
For example, if the project uses _Flow_ for one component, the user might want to use the same option for every component he creates thanks to the CLI.
{{% /notice %}}

That is the reason why **Reacli** embeds a feature enabling the user to add a `.reacli` file at the root of the project. 

The CLI will then find the root of the project and check if there is a `.reacli` file there. If that is the case, it will load it and add its content to the options given at runtime.

For example, let's imagine there is a `.reacli` file like the following.

```json
{
  "flow": true,
  "scss": true
}
```

If the user calls 

```bash
reacli component ./my-super-component --redux
```

The generated component will use the following options:

- _Flow_
- _SCSS_
- _Redux_

{{% notice warning %}}
In the `.reacli` file, **do not** write options you do not want to use (even with the `false` value). Options in the `.reacli` files are prevalent over the ones given to the CLI at runtime.
{{% /notice %}}

## Available options

Up to now, here are the lines you can write in the `.reacli` file to select options:

- `"scss": true`
- `"flow": true`
- `"redux": true`