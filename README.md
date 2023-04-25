![tea](https://tea.xyz/banner.png)

<p align="center">
  <a href="https://twitter.com/teaxyz">
    <img src="https://img.shields.io/twitter/follow/teaxyz?style=flat&label=%40teaxyz&logo=twitter&color=2675f5&logoColor=fff" alt="Twitter" />
  </a>
  <a href="https://discord.gg/JKzuqrW9">
    <img src="https://img.shields.io/discord/906608167901876256?label=discord&color=29f746" alt="Discord" />
  </a>
  <a href="#">
    <img src="https://img.shields.io/github/v/release/teaxyz/cli?label=tea/cli&color=ff00ff" alt="Version" />
  </a>
</p>

The Open Store.


# Developing `tea/gui`

To develop within an Electron view:

```sh
xc setup  # only required once
xc build  # only required if you modify the backend
xc dev    # opens the app in dev mode
```

# Contributing to `tea/gui`
If you have suggestions or ideas, start a [discussion]. If we agree, we’ll move it to an issue. Bug fixes straight to pull request or issue please!


# Releasing `tea/gui`

Tag any commit in the main branch, then push directly to the main branch.
Lets follow the [semver] versioning standard, prefixed with `v`:

```
$ git tag v1.0.0
$ git push origin tag v1.0.0
```

Refer to each package `README.md` for instructions on how to setup and
contribute to them:

* [tea/desktop](./modules/desktop/README.md)
* [tea/ui](./modules/ui/README.md)

&nbsp;



# Tasks

The following can be run with [`xc`], eg. `xc build`

## Setup
Setup ensures that required configuration placeholder files are present and installs dependencies.

```sh
if [ ! -e modules/desktop/electron/config.json ]; then
  echo '{}' > modules/desktop/electron/config.json
fi

if [ ! -e modules/desktop/.env ]; then
  cp modules/desktop/.env.example modules/desktop/.env
fi
pnpm install
```

## Build

```sh
pnpm install
pnpm build:desktop
```

## Dev

```sh
pnpm install
pnpm dev
```

## Prettier

```sh
pnpm run -r format
```

## Dist

```sh
pnpm install
pnpm --filter tea exec pnpm predist
pnpm --filter tea exec pnpm dist
```

## Check
Runs the typescript compiler and linter.

```sh
pnpm run -r check
pnpm run -r lint
```

# Dependencies

| Project                           |  Version  |
|-----------------------------------|-----------|
| nodejs.org                        | =18.15.0  |
| pnpm.io                           | =7.18.2   |
| xcfile.dev                        | >=0.0.110 |
| python.org                        | >=3.10    |

[aws/cli]: https://aws.amazon.com/cli/
[`xc`]: https://xcfile.dev
[semver]: https://semver.org
[notion]: https://www.notion.so/teaxyz/tea-gui-fdd9f50aa980432fa370b2cf6a03cb50
[discussion]: https://github.com/orgs/teaxyz/discussions
