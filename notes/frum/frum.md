# `frum`

Ruby version manager. Built with Rust, fast, has own language installer (doesn't need additional program).

## Install (with Brew)

```sh
brew install frum
```

Make sure `frum` is available. Add to `~/.zshrc`:

```sh
eval $(/opt/homebrew/bin/brew shellenv)
eval "$(frum init)"
```

## List Available Versions to Install

```sh
frum install -l
```

## Install Version of Ruby

```sh
frum install 3.2.1
```

## List Installed Versions

```sh
frum versions
```

## Set Global Version

```sh
frum global 3.2.1
```

## Set Local Version

In directory, create `.ruby-version` with version specified. Make sure the version is installed. Run:

```sh
frum local
```

## Troubleshooting

If failed to build Ruby on Apple chip:

1. Install `libffi` and `libyaml`:

```sh
brew install libffi
brew install libyaml
```

2. Export flags in `~/.zshrc`:

```sh
export LDFLAGS="-L/opt/homebrew/opt/libffi/lib"
export CPPFLAGS="-I/opt/homebrew/opt/libffi/include"
export PKG_CONFIG_PATH="/opt/homebrew/opt/libffi/lib/pkgconfig"
```
