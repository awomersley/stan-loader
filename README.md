# STAN Loader [![Build Status](https://travis-ci.org/awomersley/stan-loader.svg?branch=master)](https://travis-ci.org/awomersley/stan-loader) [![Code Climate](https://codeclimate.com/github/awomersley/stan-loader/badges/gpa.svg)](https://codeclimate.com/github/awomersley/stan-loader) [![Codacy Badge](https://www.codacy.com/project/badge/b0fdb35b7b3a4d6e92b66a75cd4a1e4d)](https://www.codacy.com/public/a/stan-loader)

A really simple native non render blocking javascript loader that will load an array of libraries in order and then execute a callack function on load or error. Will allow for higher speedtest scores on [Page Speed](https://developers.google.com/speed/pagespeed/), [ySlow](http://yslow.org/), [Site Speed](http://www.sitespeed.io/) and [Pingdom](http://tools.pingdom.com/fpt/).

```javascript
$STAN_Load(libs, success, error [,force]);
```

`libs` an array of libraries to load
`success` and `error` functions to call on load sucess/error
`force` by default libraries start to be loaded once the window load event is fired, to force them to start loading straight away set this value to true. This value is optional, to have the libraries start loading on window load you can leave this option out.

## Usage

Add the following before the closing body tag.

```javascript
<script src='stan-loader.min.js'></script>
<script>
    $STAN_Load([
        '//code.jquery.com/jquery-1.10.1.min.js',
        '//netdna.bootstrapcdn.com/bootstrap/3.0.0/js/bootstrap.min.js'
    ], function(){
      console.log("Load complete");
    }, function(){
      console.log("Load failed");
    });
</script>
```

> For optimum performance include the contents of stan-loader.min.js directly in the html.

## Install

Install via git or bower.

```
git clone git@github.com:awomersley/stan-loader.git
bower install stan-loader
```


## Browser Compatibility

STAN Loader has been tested on all modern browsers - see the matrix from Sauce Labs below. Note that in IE8 the success callback is called even on error.

[![Sauce Test Status](https://saucelabs.com/browser-matrix/stan-loader.svg?auth=d83fbc6cd64b33ed71f758b863f47d9d)]


### Copyright and License

Copyright 2015 [Andrew Womersley](https://plus.google.com/+AndrewWomersley) - Smart Arts UK Ltd under [the MIT license](LICENSE).
