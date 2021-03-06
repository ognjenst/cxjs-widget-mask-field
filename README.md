CxJS Mask Input Field
---
[![npm version](https://badge.fury.io/js/cx-mask-input-field.svg)](https://badge.fury.io/js/cx-mask-input-field) [![Node.js Package](https://github.com/ognjenst/cxjs-widget-mask-field/actions/workflows/npm-publish.yml/badge.svg?branch=master)](https://github.com/ognjenst/cxjs-widget-mask-field/actions/workflows/npm-publish.yml) <img src="https://img.shields.io/npm/dm/cx-mask-input-field" alt="downloads" />
---
![NPM](https://img.shields.io/badge/NPM-%23000000.svg?style=for-the-badge&logo=npm&logoColor=white) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB) 
--

Text Field component that allows you to add a custom mask on it. **_You need to bind the value to the store!_**
## Install

Mask Input Field can be installed with both Yarn and NPM:

`yarn add cx-mask-input-field`

`npm install cx-mask-input-field`

### You need to change the following loader in webpack.config.js:

```jsx
...
    {
        test: /\.js$/,
        include: [p('common'), p('app'), /packages[\\\/]cx/, /node_modules[\\\/](cx|cx-react|cx-theme-\w*|cx-google-maps)[\\\/]/,
        use: { loader:  'babel-loader', options:  babelCfg },

    }
...
```

Into:
```jsx
...
    {
        test: /\.js$/,
        include: [p('common'), p('app'), /packages[\\\/]cx/, /node_modules[\\\/](cx|cx-.+)[\\\/]/,],
        use: { loader: 'babel-loader', options: babelCfg },
    }
...

```

## Properties
### `mask` : `string`
Mask string. Default format characters are:<br/>

`9`: `0-9`<br/>
`a`: `A-Z, a-z`<br/>
`*`: `A-Z, a-z, 0-9`

Any character can be escaped with a backslash. It will appear as a double backslash in JS strings. For example, a German phone mask with unremoveable prefix +49 will look like

```jsx
import { MaskInputField } from  'cx-mask-input-field';

<MaskInputField  value-bind="data1"  mask="+4\\9 99 999 99"  />;
<MaskInputField  value-bind="data2"  mask={'+4\\\\9 99 999 99'} />;
```

### `maskPlaceholder` : `string`
Character to cover unfilled parts of the mask. Default character is "\_". If set to null or empty string, unfilled parts will be empty as in ordinary input.

## Packages and Libraries
### react-input-mask
Component is based on [react-input-mask](https://www.npmjs.com/package/react-input-mask) component, which is wrapped in CxJS Widget. This makes it functional out-of-the-box, once you have bind value in the store.

## Example
```jsx
import { MaskInputField } from  'cx-mask-input-field';

<MaskInputField  value-bind="data"  mask="99.99.99.99"  maskPlaceholder="_"  />;
```
## License
This component is available under the terms of [the MIT license](LICENSE.md).