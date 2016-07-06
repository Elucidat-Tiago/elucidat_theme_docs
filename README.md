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
