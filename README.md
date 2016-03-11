# Heroku Buildpack: Gb

This is the [Heroku buildpack][buildpack] for [Go][go] projects
organized as prescribed by [gb][gb] tool.

It requires that `gb` itself is also vendored just like any other
third-party packages your project might be using.

This buildpack will detect your repository as `Go (GB)` if it
contains a `.go` file under `src/...` or `vendor/src/...`.

## Usage

Ensure your Heroku app is wired to use this buildpack:

    heroku buildpacks:set https://github.com/paxan/heroku-buildpack-gb.git

This buildpack strives to default to the latest release of Go, but you can
override it if necessary. For example:

    heroku config:set GOVERSION=1.5.1

## Credits

The source code found here has been remixed from the original
[Go buildpack.][hbgo]

The simplicity of the build step in `bin/compile` script can be blamed
entirely on [gb][gbrepo] by [@davecheney](https://github.com/davecheney).

[go]: http://golang.org/
[buildpack]: http://devcenter.heroku.com/articles/buildpacks
[gb]: http://getgb.io/
[gbrepo]: https://github.com/constabulary/gb
[hbgo]: https://github.com/heroku/heroku-buildpack-go/graphs/contributors
