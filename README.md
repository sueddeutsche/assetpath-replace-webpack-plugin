# stats-replace-webpack-plugin
This plugin replaces a placeholder string in a given text asset with the name of another regex-matched asset.

For example you can replace a script/link src placeholder in your html with the final name of your js/css asset.

Tested with Node.js 6.

## Advantages
Compared to other solutions, that modify the bundled files after the webpack build, this plugin is better integrated into webpack and because of this comes with a few advantages.
* Integrated into the build process, before optimization. Therefore the chance of e.g. messed up HTML is reduced
* Works with webpack-dev-server and other tools out of the box
* Lightweight and super fast

## Example
See the `example` folder

## API
### new StatsReplacePlugin()
Array of option objects in the following format:
* .asset {String}: Path of the asset whose content is changed by this plugin (e.g. "index.html" or "frontend/index.htm")
* .basename {Boolean}: If set to false only the basename of the matched assets are inserted into your main asset. In the default configuration (false) the whole path to the matched asset is inserted.
* .replacers {Object[]}: Array of replacer definitions. The plugin first looks if it can find a webpack asset that matches the regex provided as `asset` property. If yes it replaces all matches of the `find` regex with the name of the matched assets. Sounds complicated, but is pretty ease :simple_smile:. Just have a look at the `example` folder.


## ToDo
Pull requests welcome! :+1:

* Add tests + Travis CI integration
* Add support for SourceMapSource
* Add support for files that are not part of the same webpack module
* Add support for external files that are not even in another webpack module of the same compilation
* Add CONTRIBUTORS.md
