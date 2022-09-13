# Heroku Buildpack: Selected Node Modules Cleanup

Remove specific folders from the `node_modules` directory after the build process is completed.

### Why?

The maximum allowed Heroku slug size (after compression) is 300MB as a soft limit, and 500MB as a hard limit. If you're using Node.js to compile your front-end assets, but not to run your app, you may be able to save a large amount of space by deleting selected folders from the `node_modules` directory before slug compilation.

## Usage
Adjust the index parameter based on other buildpacks in play, so that this buildpack is executed after asset compilation.

```bash
$ heroku buildpacks:set --index 1 https://github.com/leoafarias/heroku-buildpack-node-modules-cleanup
```

## Documentation

For more general information about buildpacks on Heroku:

- [Using Multiple Buildpacks for an App](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app)
- [Slug Compiler](https://devcenter.heroku.com/articles/slug-compiler)