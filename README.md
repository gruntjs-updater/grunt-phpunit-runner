# grunt-phpunit-runner

> A phpunit runner that works

## Getting Started
This plugin requires Grunt `~0.4.5`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-phpunit-runner --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-phpunit-runner');
```

## The "phpunit-runner" task

### Overview
In your project's Gruntfile, add a section named `phpunit-runner` to the data object passed into `grunt.initConfig()`.

```js
grunt.initConfig({
  phpunit-runner: {
    options: {
      // Task-specific options go here.
    },
    your_target: {
      // Target-specific file lists and/or options go here.
    },
  },
});
```

### Options

The options more or less mimic `phpunit`'s configuration parameters.

> There are 2 special cases however, the `options.extraParameters` and the
`options.phpIni`

#### options.extraParameters
Type: `Array`

If you want to pass through something that `phpunut-runner` doesn't support
Whatever you'd add in the command line, like:
```js
extraParameters: [
  '--a-new-option',
  '--another-option'
]
```

#### options.phpIni
Type: `Object`

For `phpunit`'s `-d` flag.

```js
extraParameters: {
  'parameter':'value',
  'flag': ''
}
```
will translate to `-d parameter=value -d flag`

#### options.coverageClover
Type: `string`

The equivalent of `phpunit`'s `--coverage-clover` option

#### options.coverageCrap4j
Type: `string`

The equivalent of `phpunit`'s `--coverage-crap4j` option

#### options.coverageHtml
Type: `string`

The equivalent of `phpunit`'s `--coverage-html` option

#### options.coveragePhp
Type: `string`

The equivalent of `phpunit`'s `--coverage-php` option

#### options.coverageText
Type: `string`

The equivalent of `phpunit`'s `--coverage-text` option

#### options.coverageXml
Type: `string`

The equivalent of `phpunit`'s `--coverage-xml` option

#### options.logJunit
Type: `string`

The equivalent of `phpunit`'s `--log-junit` option

#### options.logTap
Type: `string`

The equivalent of `phpunit`'s `--log-tap` option

#### options.logJson
Type: `string`

The equivalent of `phpunit`'s `--log-json` option

#### options.testdoxHtml
Type: `string`

The equivalent of `phpunit`'s `--testdox-html` option

#### options.testdoxText
Type: `string`

The equivalent of `phpunit`'s `--testdox-text` option

#### options.configuration
Type: `string`

The equivalent of `phpunit`'s `--configuration` option

#### options.bootstrap
Type: `string`

The equivalent of `phpunit`'s `--bootstrap` option

#### options.filter
Type: `string`

The equivalent of `phpunit`'s `--filter` option

#### options.testsuite
Type: `string`

The equivalent of `phpunit`'s `--testsuite` option

#### options.group
Type: `string`

The equivalent of `phpunit`'s `--group` option

#### options.excludeGroup
Type: `string`

The equivalent of `phpunit`'s `--exclude-group` option

#### options.listGroups
Type: `boolean`

The equivalent of `phpunit`'s `--list-groups` option

#### options.testSuffix
Type: `string`

The equivalent of `phpunit`'s `--test-suffix` option

#### options.reportUselessTests
Type: `boolean`

The equivalent of `phpunit`'s `--report-useless-tests` option

#### options.strictCoverage
Type: `boolean`

The equivalent of `phpunit`'s `--strict-coverage` option

#### options.strictGlobalState
Type: `boolean`

The equivalent of `phpunit`'s `--strict-global-state` option

#### options.disallowTestOutput
Type: `boolean`

The equivalent of `phpunit`'s `--disallow-test-output` option

#### options.enforecTimeLimit
Type: `boolean`

The equivalent of `phpunit`'s `--enforce-time-limit` option

#### options.disallowTodoTests
Type: `boolean`

The equivalent of `phpunit`'s `--disallow-todo-tests` option

#### options.processIsolation
Type: `boolean`

The equivalent of `phpunit`'s `--process-isolation` option

#### options.noGlobalsBackup
Type: `boolean`

The equivalent of `phpunit`'s `--no-globals-backup` option

#### options.staticBackup
Type: `boolean`

The equivalent of `phpunit`'s `--static-backup` option

#### options.columns
Type: `string`

The equivalent of `phpunit`'s `--columns` option

#### options.stderr
Type: `boolean`

The equivalent of `phpunit`'s `--stderr` option

#### options.stopOnError
Type: `boolean`

The equivalent of `phpunit`'s `--stop-on-error` option

#### options.stopOnFailure
Type: `boolean`

The equivalent of `phpunit`'s `--stop-on-failure` option

#### options.stopOnRisky
Type: `boolean`

The equivalent of `phpunit`'s `--stop-on-risky` option

#### options.stopOnSkipped
Type: `boolean`

The equivalent of `phpunit`'s `--stop-on-skipped` option

#### options.stopOnIncomplete
Type: `boolean`

The equivalent of `phpunit`'s `--stop-on-incomplete` option

#### options.verbose
Type: `boolean`

The equivalent of `phpunit`'s `--verbose` option

#### options.debug
Type: `boolean`

The equivalent of `phpunit`'s `--debug` option

#### options.loader
Type: `string`

The equivalent of `phpunit`'s `--loader` option

#### options.repeat
Type: `string`

The equivalent of `phpunit`'s `--repeat` option

#### options.tap
Type: `boolean`

The equivalent of `phpunit`'s `--tap` option

#### options.testdox
Type: `boolean`

The equivalent of `phpunit`'s `--testdox` option

#### options.printer
Type: `string`

The equivalent of `phpunit`'s `--printer` option

#### options.noConfiguration
Type: `boolean`

The equivalent of `phpunit`'s `--no-configuration` option

#### options.includePath
Type: `string`

The equivalent of `phpunit`'s `--include-path` option

#### options.version
Type: `boolean`

The equivalent of `phpunit`'s `--version` option


### Usage Examples

#### Default Options
In this example, the default options are used to do something with whatever. So if the `testing` file has the content `Testing` and the `123` file had the content `1 2 3`, the generated result would be `Testing, 1 2 3.`

```js
grunt.initConfig({
  complete: {
    options: {
      phpunit: 'vendor/bin/phpunit',
      logJunit: 'reports/unit.xml',
      coverageClover: 'reports/coverage.xml',
      colors: true
    },
    files: {
          testFiles: '**/*Test.php'
        }
    }
  }
});
```

#### Fast Options
In this example, custom options are used to do something else with whatever else. So if the `testing` file has the content `Testing` and the `123` file had the content `1 2 3`, the generated result in this case would be `Testing: 1 2 3 !!!`

```js
grunt.initConfig({
  fast: {
    options: {
      phpunit: 'vendor/bin/phpunit',
      colors: true
    },
    files: {
          testFiles: '**/*Test.php'
        }
    }
  }
});
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History
* 0.1.0 - basic functionality