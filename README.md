# Reacli landing website

The documentation is written thanks to the [GoHugo](https://gohugo.io/) framework.

See [here](https://gohugo.io/hosting-and-deployment/hosting-on-github/) to understand how it is possible to integrate a _GoHugo_ website into Github Pages.

The current repository contains the sources of the documentation website, and the built files (in the `public` folder) are directly pushed on the `master` branch of the [reacli.github.io](https://github.com/reacli/reacli.github.io) repository.

## Write the docs

### Understand the _GoHugo_ framework

To understand how to work with the _GoHugo_ framework, please refer to the [official documentation](https://gohugo.io/).

You will have to install it on your machine, and will then be able to use the _GoHugo_ CLI that facilitates the creation of new pages, chapters...

### Configure the global website

The global configuration of the website is editable in the `config.toml` file. Please refer to the [official documentation](https://gohugo.io/) to understand how it works.

We also decided to use the [**learn**](https://themes.gohugo.io/hugo-theme-learn/) theme. Please refer to its [documentation](https://learn.netlify.com/en/) to understand its functioning. It also explains how you can customize the website according to the chosen theme.

### Launch the local server

Writing the documentation is quite simple, thanks to the hot-reload functionnality. To launch a local server, run the following command:

```bash
hugo serve
```

You will then be able to connect to `http://localhost:1313`. When the server detects changes in your website sources, it will automatically reload the website.

You can finally stop the local server with `CTRL + C`.

### Documentation content

When using the CLI to create new components, chapters... it will create new folders in the `content/` directory. The markdown files in this folder correspond to the content of the website. 

## Build the docs

Once you are satisfied with the documentation you wrote, you can generate the bundle files of the landing website with the following commands:

```bash
rm -rf public/ # delete the previous bundle files
hugo -t learn # the theme to be used for the build site
```

It will regenerate the `public/` folder which contains the bundle files of the website. 

> **Important**: we configured a [git submodule](https://git-scm.com/docs/git-submodule) on the `public` folder, by running the following command:
>  ```bash
>  git submodule add -b master https://github.com/reacli/reacli.github.io.git public
>  ```
>  Precisely, when doing a commit/push on the current repository, the content of the `public/` folder (the bundle files) will be pushed directly on the `master` branch of the [reacli.github.io](https://github.com/reacli/reacli.github.io) repository.

## Deploy the docs

To upgrade the documentation website, after having built the `public/` folder (see [here](#build-the-docs)), you can simply run the following command:

```bash
./deploy.sh "feat: my commit message"
```

In the previous command, we redeployed the bundled files on the `master` branch of the [reacli.github.io](https://github.com/reacli/reacli.github.io) repository. The argument corresponds to the commit message that will be pushed on the [reacli.github.io](https://github.com/reacli/reacli.github.io) repository.

> Please refer to [conventional commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/) to understand how to write your commit messages.
