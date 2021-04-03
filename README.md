# [Flexbox Grid system maker](http://prime.one.io)

This is a **modern SCSS mixin** based on [Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes).

## Quick install

This is constantly in development! Try it out now:
You can generate grid system based on flexbox as you prefer.
- free in naming className
- free in columns per breakpoint
- free in multi columns system per breakpoint
- free in adding breakpoints
- free in gap between columns
- honestly if you are senior you are able to utilize all mixins as you prefer for your project

### NPM

```sh
npm install flex-grid-system-maker-mixin
```

**or**

### Yarn

```sh
yarn add flex-grid-system-maker-mixin
```

### Import
After installation, you can make simple grid-system with this snap shot:

```sh
@import 'flex-grid-system-maker-mixin/scss/flexbox-grid-system-maker-mixin'

$breakpointSm: 576px;
$breakpointMd: 768px;
$breakpointLg: 992px;
$breakpointXl: 1140px;

@include makeFlexRow(b-row);
@include makeFlexCols(col-, 12);

@include makeFlexGap(b-row, 10px, 10px);

@include makeFlexHelpers(flex-);
@include makeJustifyAlignHelpers();

// this should be after above so we can make it high priority than befores
@include media-breakpoint-up($breakpointSm) {
  @include makeFlexCols(sm\:col-, 3, \/3);
  @include makeFlexCols(sm\:col-, 12);
}

// this should be after $breakpointSm so we can make it high priority than befores
@include media-breakpoint-up($breakpointMd) {
  @include makeFlexCols(md\:col-, 12);
  @include makeFlexCols(md\:col-, 5, \/5);
  @include makeFlexGap(b-row, 30px, 30px);
  @include makeFlexHelpers(md\:flex-);
  @include makeJustifyAlignHelpers(md\:);
}

// this should be after $breakpointMm so we can make it high priority than befores
@include media-breakpoint-up($breakpointLg) {
  @include makeFlexCols(lg\:col-, 12);
}

// this should be after $breakpointLg so we can make it high priority than befores
@include media-breakpoint-up($breakpointXl) {
  @include makeFlexCols(xl\:col-, 12);
}

// these should be at the bottom so we can make it high priority than befores
@include makeFlexGap(small-gap, 10px, 10px);
@include makeFlexGap(no-gap, 0, 0);

```

### make Row

```sh

// makeFlexCols(<className>);

@include makeFlexCols(b-row);

// now we can use <div class="b-row">...</div>
```

### make Columns

```sh

// @include makeFlexCols(<classNamePrefix>, <columns>, <classNameSuffix>);
// className will generated as <classNamePrefix><col><classNameSuffix>

@include makeFlexCols(col-, 5, \/5);

/* now we can use 
    <div class="b-row">
        <div class="col-2/5">2/5</div>
        <div class="col-3/5">3/5</div>
    </div>
*/
```

### make gap between cols

```sh

// @include makeFlexGap(<className>, <gapX>, <gapY>);
// 

@include makeFlexGap(b-row, 20px, 20px);

/* now the cols inside b-row will be spaced 30px 
    <div class="b-row">
        <div class="col-2/5">2/5</div>
        <div class="col-3/5">3/5</div>
    </div>
*/
```

### make helpers

```sh
// @include makeFlexHelpers(<classPrefix>);
// @include makeJustifyAlignHelpers(<classPrefix>);

@include makeFlexHelpers(flex-);
@include makeJustifyAlignHelpers(b-);

/*  now we can use as
    <div class="b-row b-just-center b-align-center">
        <div class="col-1/5 flex-grow flex-order-1">2/5</div>
        <div class="col-2/5 flex-order-0">3/5</div>
    </div>
*/
```

### make breakpoint

```sh

/* media-breakpoint-up(<minWidth>) */

@include media-breakpoint-up(768px) {

  @include makeFlexCols(md\:col-, 12);
  @include makeFlexCols(md\:col-, 5, \/5);

  @include makeFlexGap(b-row, 30px, 30px);

  @include makeFlexHelpers(md\:flex-);
  @include makeJustifyAlignHelpers(md\:);
}

```

Feel free to customize.

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
