---
title: "Extension"
date: 2019-02-18T19:44:08+01:00
weight: 6
---

## Explanation

By default, generated hooks or components files have the `.jsx` extension.
Some users might want those files to have the `.js` extension.

## Usage

You can create a component (same for hooks) with the `.js` extension using: 
```bash
reacli component ./my-super-component --extension js
```

It will generate a structure like this:
```text
    .
    └── my-super-component
        ├── components
        |   ├── MySuperComponent.js
        |   ├── MySuperComponent.css
        |   └── MySuperComponentContainer.js
        └── index.js
```


### Possible extensions

Extension values can be: 

- *jsx* (default)
- *js*
