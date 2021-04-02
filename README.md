# [Flexbox Grid system maker](http://prime.one.io)

This is a **modern SCSS mixin** based on [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes).

## Quick install

This is constantly in development! Try it out now:

### NPM

```sh
npm install flex-grid-system-generator-mixin
```

**or**

### Yarn

```sh
yarn add flex-grid-system-generator-mixin
```

### Import
After installation, you can import the SCSS file into your project using this snippet:

```sh
@import 'flex-grid-system-generator-mixin/src/mixins/flex-grid-system-maker-mixins.scss'
```

Feel free to raise an issue or submit a pull request.

## CSS only

This is a **SCSS** mixin for make grid system as you prefer.

There is **no** JavaScript included. People generally want to use their own JS implementation (and usually already have one). This can be considered "environment agnostic": it's just the style layer on top of the logic.

## Browser Support

This uses [autoprefixer](https://github.com/postcss/autoprefixer) to make (most) Flexbox features compatible with earlier browser versions. According to [Can I use](https://caniuse.com/#feat=flexbox), This is compatible with **recent** versions of:

* Chrome
* Edge
* Firefox
* Opera
* Safari

Internet Explorer (10+) is only partially supported.
