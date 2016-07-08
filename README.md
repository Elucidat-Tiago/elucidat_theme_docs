# elucidat_theme_docs
Theme Documentation for Elucidat Parts Feature

### Quick Tips

Classes that begin with `e-` eg `e-float--left` do not affect similar items changes

The Mixins tab gets put at the start of the parts file.  When the file is saved it compiles the SASS into CSS, leaving space for the variables that look like `/*R your_variable*/` for this reason it is advised to AVOID using `/*` to comment out lines and instead only `//` to avoid potential errors.

## Colourways

A basic variable in the colourways consists of a `variable` (which is the corresponding variable name in the SASS without the `$` symbol at the start, a default value for the variable, a type which can be slider, image, font or list, if a type isn't set then the type is a colour picker.

###### A regular Colour Variable
```
{
    "variable": "body-bg",
    "default": "#F9F9F9"
},
```

###### An Image Variable
```
{
    "variable": "client-logo",
    "default": "url({{media.1149655}})",
    "type": "image"
},
```

###### A Slider Variable
```
{
    "variable": "base-font-size",
    "default": "16px",
    "type": "slider",
    "min": "9px",
    "max": "21px"
},
```
###### Font Variables
```
{
    "variable": "display-font",
    "default": "Arial",
    "type": "font"
},
{
    "variable": "copy-font",
    "default": "Arial",
    "type": "font"
},
```
###### A List Variable
```
{
    "variable": "icon-path",
    "default": "fontawesome",
    "type": "list",
    "options": {
        "Material": "material",
        "FontAwesome": "fontawesome",
        "Typicon": "typicon"
    }
}
```

## Important Variables

`$base-unit` is used for padding and margin calculations, default is 16px
`$text-direction` text direction, either ltr (default) or rtl
`$body-bg` background colour for the body
`$text-color` and `$text-color-neutral`
`$nav-color` `$nav-color-neutral` used for navigation, progress bars and navigation percentage
`$interaction-color` and `$interaction-color-neutral` used for resources inner list item hover, primary buttons, secondary buttons(inverted), card overlay (inverted), media controls, primary icon colours, secondary icon colours (inverted), neutral is used for image caption and card caption backgrounds, caption subtext, explorer item backgrounds and borders, link overlays, chapter percentage backgrounds and bar, accordion openeed hover, radio buttons, likert selected answers and sliders, droppers, sortable items, modal backgrounds and popover close.
`$action-color` and `$action-color-neutral` used for action button.
```
// border radius for different items
$border-radius: 3px;
$button-radius: 3px;
$icon-radius: 50%;

// placeholder image
$placeholder-image: url({{media.1138718}});

// client logo
$client-logo: url({{media.1149655}});

// fonts
$display-font: Arial; // font used for titles
$copy-font: Arial; //font used for regular text



// advanced

// max width for the content
$content_max_width: 1110px;
// margin for when the screen size is smaller than the content-max_width
$content_margin: bu(1);
$content_margin--mobile: bu(0.5);


$soft_border-width: 1px;
$soft_border-color: rgba(0,0,0,0.12);
$soft_border: $soft_border-width solid $soft_border-color;


// colors for the questionnaire feedback
$correct-color: #B5BF01;
$partial_correct-color: #F8BB86;
$incorrect-color: #EE1C2E;


// padding for item consistency
$itemInner-vertical-padding: bu(1.5);
$itemInner-horizontal-padding: bu(1);

$padding-compact: bu(1) bu(1);
$padding-large: bu(1.5);

// box-shadow
$no-shadow: 0 0;
$shadow0: 0 0 0 0 rgba(0, 0, 0, 0), 0 0 0 0 rgba(0, 0, 0, 0); // shadow
$shadow1: 0 2px 5px 0 rgba(0, 0, 0, 0.16), 0 2px 10px 0 rgba(0, 0, 0, 0.12); // floating element 'on rest'
$shadow2: 0 5px 11px 0 rgba(0, 0, 0, 0.18), 0 4px 15px 0 rgba(0, 0, 0, 0.15); // floating element 'on hover'


// border-radius
$border-radius-top: $border-radius $border-radius 0 0;
$border-radius-bottom: 0 0 $border-radius $border-radius;
$border-radius-right: 0 $border-radius $border-radius 0;
$border-radius-left: $border-radius 0 0 $border-radius;


// typography

$base-font-size: 16px;

$display-4: $base-font-size * 8;
$display-3: $base-font-size * 4;
$display-2: $base-font-size * 3.2;
$display-1: $base-font-size * 2.42;

$headline: $base-font-size * 1.71;
$subhead: $base-font-size * 1.14;

$title: $base-font-size * 1.42;
$caption: $base-font-size * 0.85;


// base spacing

$base-spacing: bu(1);
$base-spacing--mobile: $base-spacing * 0.5;

// focus helper

$focus_helper_color: rgba(0,0,0,0.06);

// grid

$grid-margin: 1%;

// tooltip
$tooltip-width: 200px;

// modal
$modal_background_color: $text-color-neutral;


//mejs

$mejs-control-icon-size: 16px;
$mejs-control-height: bu(2);
$mejs-bar-height: bu(0.25);
$mejs-controls-background: $text-color-neutral;
$mejs-bar-color: $interaction-color;
$mejs-button-color: $text-color;
$mejs-button-hover-color: $interaction-color;


// accordion
$accordion-group-spacing: $base-spacing / 4;

// tabs
$tab-gutter: 0; // spacing between nav-tabs and tab-pane
$tab-spacing: 0; // spacing between each tab

```

## Base Mixins

`base-spacing` margin top and bottom
`horizontal-padding` padding left/right based on $base-spacing
`vertical-padding` padding top/bottom
`clearfix` :before & :after `content=""; display: table; line-height: 0;` and :after `clear: both`
`prefix($property, $value)` applies all the browser/webkit prefixes to property and assigns value eg `-ms-#{$property}: $value;`
`transform($transform)` applies transform for all browsers prefixes eg `-webkit-transform: $transform;`
`transition($transition)` applies transition to all browser prefixes eg `-webkit-transition: $transition;`
`transition-2($transition1, $transition2)` applies transition to all browser prefixes eg `-webkit-transition: $transition1, $transition2;`
`main-transition` applies a transition of `all 0.4s ease-in-out 0s` as standard
`short-transition` applies a transition of `all 0.2s ease-in-out 0s`
`long-transition` applies a transition of `all 0.6s ease-in-out 0s`
`no-transition` applies `transition: none`
`animation($animation)` applies browser prefixes to animation eg `-webkit-animation: $animation;`
`keyframes($animationName)` applies browser prefixes to keyframes animation eg 
```
@-webkit-keyframes #{$animationName} {
    @content;
}
```
`placeholder-image` applies the $placeholder-image, background size to cover, position 50% 50% and no-repeat
`linearGradient($top, $bottom)` applies a background to linear gradient with browser prefixes
`gradient($direction, $g-color-1, $g-color-2)` applies a background gradient
`content-width` sets `max-width: $content_max_width;` and padding left/right to `$content_margin` etc
`full-width` sets width to auto and max-width to none, padding left/right to `$content_margin`
`module-base` module base set up
`e-hover-parent` forces edit control to show if you hover a child element
`e-hover-parent-inset`
`card-base` card base set up


# Styling

## Buttons

#### Sizes
`e-button--small`, `e-button--large`

#### Floats
`e-float--start`, `e-float--end`, `e-float--center`

## Menus

`.project__menu`
`.project__menu.open`
`.project__menu .menu__wrap`
