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
```

## Buttons
