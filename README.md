# CCgram

[![Build Status](https://travis-ci.org/EastSun5566/cc-gram.svg?branch=master)](https://travis-ci.org/EastSun5566/cc-gram) [![npm](https://img.shields.io/npm/v/cc-gram.svg)](https://www.npmjs.com/package/cc-gram)

> 🖼 A CSS & Canvas Instagram filters based on CSSgram

## ✨ Install

```sh
npm i cc-gram

# or yarn add cc-gram
```

## 🚀 Usage

### Apply CSS filter

#### HTML

> An image tag with `data-filter` attribute is filter name

```html
<img src="./my-picture.png" data-filter="1977" />
```

#### JavaScript

> Initialize to apply CSS filter to All targets has `data-filter` attribute

```js
import CCGram from "cc-gram";

const cg = new CCGram();
```

---

##### Manual apply CSS filter

> `applyFilter()`

```js
cg.applyFilter();
```

##### All available filter name list

> `filterNames`

```js
const { filterNames } = cg;
```

##### Add / Set filter to filter list

> `setFilter(name, setting)`

- name: `string` - The filter name
- setting: `object` - The filter setting

```js
cg.setFilter("my-filter", {
  saturate: 0.8,
  contrast: 1.2
});
```

- Available setting key (all value is number):

  - `blur`
  - `brightness`
  - `contrast`
  - `grayscale`
  - `hue-rotate`
  - `invert`
  - `saturate`
  - `sepia`

##### Remove filter from filter list

> `removeFilter(name)`

- name: `string` - The filter name

```js
cg.removeFilter("my-filter");
```

---

### Access Filter image

```js
const target = document.querySelector('img[data-filter="1977"]');
```

#### Data URL

> `getDataUrl(element[, options = {}])`

```js
const dataUrl = await ccGram.getDataUrl(target);
```

#### Blob

> `getBlob(element[, options = {}])`

```js
const blob = await cg.getBlob(target, {
  type: "image/jpeg",
  quality: 0.8
});
```

- Options

  - type: `string` - MIME types, default is `image/png`,
  - quality: `number`- [0 - 1], default is `0.92`

## 🔧 Develop

```sh
# Install dependencies
yarn

# Fix style
yarn lint

# Run test
yarn test

# Build for production
yarn build
```
