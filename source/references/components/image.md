---
title: <image>
type: references
group: Build-in Components
order: 8.02
version: 2.1
---

`<image>` is used to render a specified picture, and it shouldn't contain any child component. `<img>` is not supported currently.

## Basic Usage

> **Note:** the styles of `width` and `height` should be specified, otherwise it won't work.

```html
<image style="width:500px;height:500px" src="https://vuejs.org/images/logo.png"></image>
```

See the [real result](http://dotwe.org/vue/00f4b68b3a86360df1f38728fd0b4a1f).

## Attributes

| Attribute | Type | Value | Default Value |
| - | - | - | - |
| `placeholder` | String | {URL &#124; Base64} | - |
| `resize` | String | conver &#124; contain &#124; stretch | stretch |
| `src` | String | {URL &#124; Base64 } | - |

### `placeholder`

### `resize`

![image resize property](../images/image-resize-property.png)

+ `contain`: balala. ([Example](http://dotwe.org/vue/89be94dcd1fec73b77246ec46c678914))
+ `cover`: balala. ([Example](http://dotwe.org/vue/f38e311d2e6b2af87f0a65a8f37d9490))
+ `stretch`: [default] balala. ([Example](http://dotwe.org/vue/f38e311d2e6b2af87f0a65a8f37d9490))

CSS [`background-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size).

### `src`

> **Note**: src path. balala.

#### Supported image formats

Depends on your image libs. balala.

## Component Methods

> What's the component method?

### `save` <span class="api-version">v0.16.0+</span>

Save photo. balala.

**Parameters**:

+ `callback`: {Function}

Callback function parameters:

+ `success`: {Boolean}
+ `errorDesc`: {Object}

**Return value**: null

> **Note**: You must add `NSPhotoLibraryAddUsageDescription` and `NSPhotoLibraryAddUsageDescription` (iOS 11) privacy to access photo album for iOS.

#### Use `save` Method

Add `ref` attribute (Vue.js *[Child Component Refs](https://vuejs.org/v2/guide/components.html#Child-Component-Refs)*) on `<image>`:

```html
<image ref="poster" src="path/to/image.png"></image>
```

Get the component reference and use the `save` method:

```js
const $image = this.$refs.poster
$image.save(result => {
  if (result.success) {
    // TODO
  } else {
    console.log(result.errorDesc)
  }
})
```

See the [full example](http://dotwe.org/vue/4624d605004fc7eb9f14ca9c5a226fe3).

## Events

Support **[common events](../../wiki/common-events.html)**: `click`, `longpress`, `touchstart`...

### `load`

Trigger when image is loaded. balala.

**Event object**:

+ `success`: {Boolean} balala.
+ `size`: {Object} balala.
  + `naturalWidth`: {Number} balala.
  + `naturalHeight`: {Number} balala.

#### Handle `load` Event

Bind `load` event on `<image>`:

```html
<image @load="onImageLoad" src="path/to/image.png"></image>
```

Add event handler:

```js
export default {
  methods: {
    onImageLoad (event) {
      if (event.success) {
        // TODO
      }
    }
  }
}
```

See the [full example](http://dotwe.org/vue/4624d605004fc7eb9f14ca9c5a226fe3).

## Styles

`<image>` is block level.

Support **[common styles](../../wiki/common-styles.html)**.

## Usage Notes

+ No children

## Examples

+ [Base64 image](http://dotwe.org/vue/4624d605004fc7eb9f14ca9c5a226fe3)
+ [Multi-layer images](http://dotwe.org/vue/4624d605004fc7eb9f14ca9c5a226fe3)
+ [Lazy load image](http://dotwe.org/vue/4624d605004fc7eb9f14ca9c5a226fe3)
