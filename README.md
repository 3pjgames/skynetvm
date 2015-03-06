# skynetvm

[skynet](https://github.com/cloudwu/skynet) version manager

## Installation

Just copy `skynetvm` into any directory in your `PATH`, or use [fresh](http://freshshell.com/)

    fresh 3pjgames/skynetvm skynetvm --bin

## Usage

### skynetvm install version

Install specified `version`. The version can be the skynet git repository branch or tag, such as `lua53`, `master`, `v0.7.4`.

The versions will be installed into `~/.skynetvm/versions`.

To uninstall a version, just delete the corresponding directory in `~/.skynetvm/versions`.

Examples:

    $ skynetvm install v0.7.4

### skynetvm default

Get current default skynet version. This version is used when version is ommitted in `exec` and `skynet` subcommands.

    $ skynetvm default
    v0.7.4

### skynetvm default version

Set a version a default version

    $ skynetvm default master
    $ skynetvm default
    master

### skynetvm versions

List installed versions.

### skynetvm skynet \[version\] configfile

Run skynet with specified version and config file. The version is optional. The environment variable `SKYNET_ROOT` is set to the skynet root directory, and it is also added to `PATH`. See the [example config](https://github.com/3pjgames/skynetvm/blob/master/example) that how to setup `lua_path` and `lua_cpath`.

    $ skynetvm skynet example

### skynetvm exec \[version\] command \[options\]

Run an arbitrary command with `SKYNET_ROOT` environment exported.
