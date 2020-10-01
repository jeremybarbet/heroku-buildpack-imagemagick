# heroku-buildpack-imagemagick

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) working with [`heroku-18`](https://devcenter.heroku.com/articles/stack) for vendoring the ImageMagick binaries into your project.

### Install

In your project root:

`heroku buildpacks:add https://github.com/jeremybarbet/heroku-buildpack-imagemagick --index 1 --app HEROKU_APP_NAME`

### Changing version

- Go to https://www.imagemagick.org/download/releases
- Find `*.tar.gz` and download it to the project's root
- Update `IMAGE_MAGICK_VERSION` in `bin/compile`
- Clear cache, as shown below, and redeploy your app to Heroku.

### Clear cache

Since the installation is cached you might want to clean it out due to config changes.

1. `heroku plugins:install heroku-repo`
2. `heroku repo:purge_cache --app HEROKU_APP_NAME`
