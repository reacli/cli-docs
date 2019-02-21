---
title: "Scss"
date: 2019-02-18T19:44:08+01:00
weight: 5
---

## Explanation

By default, the style file associated to a generated dumb component is a `.css` file.

Some users might want to use _Sass_. That is the reason why we added the `--scss` argument. _SCSS_ is a _Sass_ syntax that is also full compatible with the _CSS_ syntax.

In other words, it means that every valid _CSS_ stylesheet is a valid _SCSS_ file with the same meaning.

## Usage

You can generate an `.scss`-styled component using the following command: 
```bash
reacli component ./my-super-component --scss
```

It will generate a structure like this:
```text
    .
    └── my-super-component
        ├── components
        |   ├── MySuperComponent.jsx
        |   ├── MySuperComponent.scss
        |   └── MySuperComponentContainer.jsx
        └── index.js
```

It will only have an impact on the dumb component, which will look like the following:

![scss-dumb-component](/options/images/scss-dumb-component.png?width=70%)

The only change in the dumb component above shown is the import of the _SCSS_ file instead of the default _CSS_ one.