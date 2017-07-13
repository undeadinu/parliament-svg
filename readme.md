# parliament-svg

Generate parliament charts as **[virtual-dom](https://github.com/Matt-Esch/virtual-dom#virtual-dom) SVG**. Design inspired by the [Wikipedia parliament charts](https://github.com/slashme/parliamentdiagram).

[![npm version](https://img.shields.io/npm/v/parliament-svg.svg)](https://www.npmjs.com/package/parliament-svg)
[![dependency status](https://img.shields.io/david/juliuste/parliament-svg.svg)](https://david-dm.org/juliuste/parliament-svg)
[![dev dependency status](https://img.shields.io/david/dev/juliuste/parliament-svg.svg)](https://david-dm.org/juliuste/parliament-svg#info=devDependencies)
[![license](https://img.shields.io/github/license/juliuste/parliament-svg.svg?style=flat)](LICENSE)
[![chat on gitter](https://badges.gitter.im/juliuste.svg)](https://gitter.im/juliuste)

## Installation

```shell
npm install --save parliament-svg
```

## Usage

```js
const parliamentSVG = require('parliament-svg')

const svg = parliamentSVG(parties, seatCount)
```

- `parties` is an object containing seat count and colour for each party

```json
{
	"linke": {
		"seats": 64,
		"colour": "#a08"
	},
	"spd": {
		"seats": 193,
		"colour": "#e02"
	},
	"gruene": {
		"seats": 63,
		"colour": "#0b2"
	},
	"union": {
		"seats": 311,
		"colour": "#333"
	}
}
```
Each seat contains the party name in its `class` attribute.

- `seatCount` is a boolean, if `true` the total seat count will be displayed in the chart

For the given `parties` object and `seatCount` enabled, the rendered result should look like this:

![Example: German Bundestag with seat count enabled](https://rawgit.com/juliuste/parliament-svg/master/example/seatCount.svg)

If you want to convert the virtual DOM tree to HTML/SVG string, use `virtual-dom-stringify`:

```js
const toStr = require('virtual-dom-stringify')
const svg = toStr(svg)
```

## Contributing

If you found a bug, want to propose a feature or feel the urge to complain about your life, feel free to visit [the issues page](https://github.com/juliuste/parliament-svg/issues).
