# skynetvm

[skynet](https://github.com/cloudwu/skynet) 版本管理

## 安装

把 `skynetvm` 复制到包含在 `PATH` 中的目录即可，或者通过 [fresh](http://freshshell.com/)

    fresh 3pjgames/skynetvm skynetvm --bin

## 使用

### skynetvm install version

安装指定 `version` 的 skynet。版本可以是 skynet git 仓库中的 branch 或者 tag，例如 `lua53`, `master`, `v0.7.4`.

所有版本都会安装到 `~/.skynetvm/versions`.

卸载只需要把 `~/.skynetvm/versions` 下相应目录删除即可。

例子：

    $ skynetvm install v0.7.4

### skynetvm default

获得当前默认的 skynet 版本。当子命令 `exec` 和 `skynet` 省略版本时会时候该默认版本。

    $ skynetvm default
    v0.7.4

### skynetvm default version

设置一个默认的 skynet 版本

    $ skynetvm default master
    $ skynetvm default
    master

### skynetvm versions

列出已经安装的版本

### skynetvm skynet \[version\] configfile

使用指定的版本和配置文件启动 skynet。版本可以省略。启动前会设置好环境变量 `SKYNET_ROOT` 指向对应版本 skynet 的根目录，该根目录也会添加进 `PATH`. 参考 [示例配置](https://github.com/3pjgames/skynetvm/blob/master/example) 如何设置 `lua_path` 和 `lua_cpath`.

    $ skynetvm skynet example

### skynetvm exec \[version\] command \[options\]

执行任意命令，该命令能够访问到环境变量 `SKYNET_ROOT`
