*This repository is a mirror of the [component](http://component.io) module [sindresorhus/is-psd](http://github.com/sindresorhus/is-psd). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/sindresorhus-is-psd`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# is-psd [![Build Status](https://travis-ci.org/sindresorhus/is-psd.svg?branch=master)](https://travis-ci.org/sindresorhus/is-psd)

> Check if a Buffer/Uint8Array is a [PSD](http://en.wikipedia.org/wiki/Adobe_Photoshop#File_format) image

Used by [image-type](https://github.com/sindresorhus/image-type).


## Install

```sh
$ npm install --save is-psd
```

```sh
$ bower install --save is-psd
```

```sh
$ component install sindresorhus/is-psd
```


## Usage

##### Node.js

```js
var readChunk = require('read-chunk'); // npm install read-chunk
var isPsd = require('is-psd');
var buffer = readChunk('unicorn.psd', 0, 4);

isPsd(buffer);
//=> true
```

##### Browser

```js
var xhr = new XMLHttpRequest();
xhr.open('GET', 'unicorn.psd');
xhr.responseType = 'arraybuffer';

xhr.onload = function () {
	isPsd(new Uint8Array(this.response));
	//=> true
};

xhr.send();
```


## API

### isPsd(buffer)

Accepts a Buffer (Node.js) or Uint8Array.

It only needs the first 4 bytes.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
