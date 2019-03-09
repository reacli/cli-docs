---
title: "Configuration file"
date: 2019-02-18T19:44:08+01:00
weight: 7
---

## Description 

Some users might want to use the _Reacli_ CLI to create several components or hooks in the same project. Each new element might have to be configured with the same options. 

{{% notice tip %}}
For example, if the project uses _Flow_ for one component, the user might want to use the same option for every component he creates thanks to the CLI.
{{% /notice %}}

That is the reason why **Reacli** embeds a feature enabling the user to add a `.reacli` file at the root of the project. 

The CLI will then find the root of the project and check if there is a `.reacli` file there. If that is the case, it will load it and add its content (with prevalence) to the options given at runtime.

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
Options in the `.reacli` files are prevalent over the ones given to the CLI at runtime.
{{% /notice %}}

## Available options

To use a global configuration, at the root of your project (next to the package.json), you can create a .reacli file. Its content, formatted as JSON, might contain the following key-value pairs:

```js
// .reacli
{
  "scss": true, // or false
  "flow": true, // or false
  "redux": true, // or false
  "extension": "js" // or jsx 
}
```

If one option is not set in your .reacli file, the default one will be used.

>Not having a .reacli file is like having one that contains:
>
>```js
>// .reacli
>{
> "scss": false,
> "flow": false,
> "redux": false,
> "extension": "jsx" 
>}
>```

## Ignoring the configuration file

When using a `.reacli` file to configure the **Reacli** tool globally for your project, it might happen that you want to ignore this configuration file when creating a new element.

To do so, you can use the `-i` or `--ignore-config-file` argument.