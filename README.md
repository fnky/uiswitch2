UISwitch II
===========

A customizable UISwitch in pure CSS3. The successor to [css3-uiswitch](https://github.com/fnky/css3-uiswitch)

> #### [Take a peek at the demo](http://codepen.io/cbp/pen/qEQRww)

## What's updated?

It's got a whole new look, which means you don't need to use a iOS 7 rip-off, but customize it to your liking. You can now customize the sizing and offset to your liking.

It still uses the same smooth transition effect as its [precessor](https://github.com/fnky/css3-uiswitch)—this might change to be customizable aswell.

## Go get it

Install using [Bower](http://bower.io/) *(recommended)*

```bash
$ bower install uiswitch2
```

... or ...

Clone repository

```bash
$ git clone https://github.com/fnky/uiswitch2.git
```

## Usage

```scss
@include uiswitch(
  $size: 50px, // The size of the button. This will be used to calculate offsets and thumb size, if they're not overriden.
  $thumb-size: $size / 3, // The size of the thumb.
  $active-thumb-size: $size / 2.25, // The size of the thumb when in `:active` state (mousedown).

  $thumb-offset: ($thumb-size / 4), // The offset of the thumb from the edges.
  $on-thumb-offset: $thumb-offset + $thumb-size, // The offset of the thumb from the edges, when the switch is checked (on).

  $on-tint: $uiswitch-on-tint, // The tint (color) of the switch, when it's checked (on).
  $off-tint: $uiswitch-off-tint, // The tint (color) of the switch, when it's unchecked (off).
  $thumb-off-tint: $uiswitch-thumb-off-tint, // The tint (color) of the thumb, when the switch is unchecked (off).
  $thumb-on-tint: $uiswitch-thumb-on-tint // The tint (color) of the thumb, when the switch is checked (on).
);
```

### CSS

You can customize it however you like, even if you're using vanilla CSS. It get's a bit tricky with customizing the size, though.

```css
/* Active Background Tint (when pressed and hold) */
.custom { background-color: #eadcbc; }

/* Background Tint */
.custom::before { background-color: #f7f2e5; }

/* Knob Tint */
.custom::after { background: #fff3a6; }

/* Checked background tint */
.custom:checked { background-color: #ffca3f; }
```

and your HTML would be something like this

```html
<input type="checkbox" class="uiswitch custom">
```

### Sass

To make things easier—and you probably do—you can use Sass. You can set the global stylings across each switch (`.uiswitch` only)

```scss
$uiswitch-thumb-tint: #ffffff !default;
$uiswitch-on-tint: #4CD964 !default;
$uiswitch-off-tint: #ffffff !default;

$uiswitch-size: 40px;
```

Or, if you'd rather make your own switch, you can do that aswell

```scss
.my-switch {
  @include uiswitch(
    $size: 40px,
    $on-tint: hotpink,
    $thumb-tint: lime,
    $off-tint: yellow);
}
```

If you'd like to customize it to the bare-bones, simply extend `%uiswitch` and do your tweaking.

```scss
.my-switch {
  @extend %uiswitch;
  border-radius: 4px;

  // Background
  &::before { border-radius: 2px; }

  // Thumb
  &::after { border-radius: 1px; }

  // Checked background
  &:checked { background: hotpink; }

  // Checked thumb
  &:checked::after { background-color: #333; }
}
```

## License

MIT
