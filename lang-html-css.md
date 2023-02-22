# HMTL/CSS Code Guidelines

Detailed below are style guidelines to be followed in HTML/CSS code, in addition to the General style guidelines.

## Formatting

**Line Character Limit**

There is no strict limit on line length for HTML, but it is highly recommended to shorten or split up excessively long lines.

**Identation**

CSS code should be idented block-style by 2 spaces.

Good example:
```css
@keyframes gradient {
  0% {
	  background-position: 0% 50%;
  }
  100% {
	  background-position: 100% 50%;
  }
}
```

## Naming

**Casing**

Use kebab case (alphanumeric characters separated by dashes) for all identifiers.

Good examples:
* `class="dotted light-blue"`
* `id="submit-button"`
* `name="section1"`

Bad examples:
* `id="Water-Bottle"`
* `class="light_pink dotted"`

**Generality**

Use concise but descriptive names for CSS identifiers. If the style can be generalized to more places, use a more general name so that the style can be used in more places.

## CSS Styling

**Inline Styling**

Avoid inline styling where possible.

**Shorthand Properties**

Use shorthand properties whenever possible.

Good example:
```css
padding: 0 5px 10px 5px;
```

Bad example:
```css
padding-top: 0;
padding-bottom: 10px;
padding-left: 5px;
padding-right: 5px;
```

**Colors**

Hex codes are preferred over RGB.