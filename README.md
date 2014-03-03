# grunt-files-to-ngmodule

> Simple grunt plugin to create a list of files and wrap it as an angularjs module

## Getting Started
This plugin requires Grunt.

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-files-to-ngmodule --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-files-to-ngmodule');
```

## The "files_to_ngmodule" task

### Overview
In your project's Gruntfile, add a section named `files_to_ngmodule` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  files_to_ngmodule: {
    files: {
      src: // [pattern],
      dest: // output file,
        options: {
          moduleName: // name of the angularjs module ,
          listName: // name of filelist array ,
          itemName: // item
       }
    }

  },
})
```

### Options

#### options.moduleName
Type: `String`
Default value: `'files'`

#### options.listName
Type: `String`
Default value: `'list'`

#### options.itemName
Type: `String`
Default value: `'item'`

### Usage Examples

```js
grunt.initConfig({
  files_to_ngmodule: {
    files: {
      src: '<%= distdir %>/themes/*/*.css',
        dest: 'src/app/themelist.js',
        options: {
          moduleName: 'themeslist',
          name: 'THEMES',
          itemName: 'theme'
       }
    }
  },
});
```
#### Example output file

```js
angular.module("themelist", [])
.constant({"THEMES": [
    {"name":"theme_1", "url":"/themes/default/8909873.style.css"},
    {"name":"theme_2", "url":"/themes/comso/8934573.style.css"},
    {"name":"theme_3", "url":"/themes/minimal/8923473.style.css"}
]});

```

## Running the tests

After you have cloned the repo execute grunt test.

## Release History
_(Nothing yet)_

## License
Copyright (c) 2014 Nik G. Licensed under the MIT license.
