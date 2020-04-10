# Vue.js Read-More

https://github.com/raublekick/read-more

Read-More is a simple plugin fo vue.js forked from https://github.com/orlyyani/read-more

I have removed the directive for simplicity.

# Github NPM package

__NOTE:__ This pacakge is hosted on GitHub.

```
 npm install raublekick/read-more --save
```

# Features!

  - Add read more length
  - Add read more link
  - Custom read more string
  - Custom read less string
  - Better defaults
  - Slot for custom links or buttons
  - v-model support
  - Align and inline options

# Usage

```
 import ReadMore from 'vue-read-more';
 
 Vue.use(ReadMore);
```

# Sample

Basic usage
```html
<read-more :text="text" />
```
Alignment
```html
<read-more :text="text" align="right" />
```
Inline
```html
<read-more :text="text" inline />
```
Removing the read less link
```html
<read-more :text="text" lessStr="" />
```
Custom controls and v-model
```html
<read-more :text="text" lessStr="read less" v-model="toggle">
  <template slot="links">
    <button v-on:click="toggle = !toggle">Toggle</button>
  </template>
</read-more>
```


# API


| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `text` (required) | `String` | `none` | `text` is used to limit the submitted string based on the `maxChars`.| 
| `maxChars` | `Number` | `100` | It is used to limit the `text` value to generate a read more text. |
| `link` | `String` | `#` | You can pass a link incase you want to redirect the user when the `moreStr` has been triggerd.
| `moreStr` | `String` | `read more` | You can customize your read more string by passing a value to `moreStr`.
| `lessStr` | `String` | `none` | You can customize your read less string by passing a value to `lessStr`.
| `align` | `String` | `left` | You can customize whether the default links align to the left or right of the container by passing `left` or `right` to `align`.
| `inline` | `Boolean` | `false` | You can control whether the links display inline or block.


# License

#### MIT
Use at your own risk!
