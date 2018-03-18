# asdf-elixir

Elixir plugin for [asdf](https://github.com/asdf-vm/asdf) version manager

## Install

> *Elixir requires Erlang to be installed. You can use the [asdf-erlang](https://github.com/asdf-vm/asdf-erlang) plugin to install Erlang versions.*

```
asdf plugin-add elixir https://github.com/asdf-vm/asdf-elixir.git
```

## Elixir precompiled versions

Precompiled Elixir packages are built by [Bob](https://github.com/hexpm/bob/blob/master/README.md#elixir-builds) whenever
a git push or a new release is made at the elixir repo.

These precompiled packages are built against every officially supported OTP version, however if you only specify the
elixir version, like `1.4.5`, the downloaded binaries will be those compiled against the oldest OTP release
supported by that version.

If you would like to use precompiled binaries built with a more recent OTP, you can append `-otp-${OTP_VERSION}` to any installable version that can be given to asdf-elixir.

So, for example, to install Elixir 1.5.0 and take advantage of the new features from OTP-20 you might install version `1.5.0-otp-20`.

Be sure to also install the correspoding Erlang/OTP version with asdf-erlang, and to have both selected versions in your
`.tool-versions` file.


## Elixir escripts support

This plugin supports elixir escripts adding them to your path just like any other elixir binary.
Whenever you install a new escript with `mix escript.install` you need to `asdf reshim elixir` in order
to create shims for it.

## Default Elixir packages

asdf-elixir can automatically install a set of default hex packages right after installing an elixir version. To enable this feature, provide a `$HOME/.default-elixir-packages` file that lists one package per line, for example:

```
hex
https://github.com/phoenixframework/archives/raw/master/phx_new.ez
github user/repo
```

This will install hex using `mix local.hex`, add the phoenix generator or install a mix package from github. For full set of options, try `mix help archive.install`.

## Use

Check [asdf](https://github.com/asdf-vm/asdf) readme for instructions on how to install & manage versions of Elixir.
