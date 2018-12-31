# Fonts

Vertical rhythm
Reset CSS/Normalizer
Font Pairing


## Compare

When designing components, look for pages with similar content and see how they solve it. Create a research pool and evaluate the strength and weaknesses of each design decisions.


## Modular Scale

Apply modular scale for fonts

## Pattern Library 

Come up with a list of common components (button, spinner) or layouts (header footer, carousel).

## A/B Testing Components

Or rather, use bandit algorithm to test components. See how frequent user interacts with the component to determine the valu of the components. Another way is to use heatmap from Hotjar.

## Colors

For naming colors, refer to `namethatcolor` website.



# Code breakdown
configuration
- constant values
- default values
- configurable values
initialization
- new state
- load existing state
rules
- business logic
- validation
- errors
security
- authorization
- signing/extraction/verification
storage
- inmemory
- persistent
- CRUD

# SCSS List
```scss
$colors: #C98910, #A8A8A8, #965A38;
@for $i from 1 through 3 {
  .user:nth-child(#{$i}) .user-position {
    color: nth($colors, $i);
    background: rgba(nth($colors, $i), .2);
  }
}
```

## Colors

```
Gold
HEX: #C98910
RGB: 201,137,16 

Silver
HEX: #A8A8A8
RGB: 168,168,168

Bronze
HEX: #965A38
RGB: 150,90,56
```
