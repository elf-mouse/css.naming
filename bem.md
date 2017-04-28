# [Block, Element, Modifier](https://en.bem.info/)

- Names of BEM entities are written using __numbers__ and __lowercase Latin characters__.
- Individual words within names are separated by a __hyphen__ (`-`).
- Information about the names of blocks, elements, and modifiers is stored using __CSS classes__.

## Block name

A block name follows the `block-name` scheme and defines a namespace for elements and modifiers.

```html
<div class="block">...</div>
```

```css
.block { color: #042; }
```

## Element name

The namespace defined by the name of a block identifies an element as belonging to the block. An element name is delimited by a double underscore (`__`).

The full name of an element is created using this scheme: `block-name__elem-name`

```html
<div class="block">
  ...
  <span class="block__elem"></span>
</div>
```

```css
.block__elem { color: #042; }
```

## Modifier name

The namespace defined by the name of a block identifies a modifier as belonging to that block or its element. A modifier name is delimited by a single underscore (`_`).

The full name of a modifier is created using the scheme:

- For Boolean modifiers — `owner-name_mod-name`.
- For key-value type modifiers — `owner-name_mod-name_mod-val`.

### Block modifier

- __Boolean modifier__. The value of such a modifier is not specified. The full name is created using the scheme: `block-name_mod-name`.
- __Key-value type modifier__. The value of a modifier is separated from its name by a single underscore (_). The full name is created using the scheme: `block-name_mod-name_mod-val`.

### Element modifier

- __Boolean modifier__. The value of such a modifier is not specified. The full name is created using this scheme: `block-name__elem-name_mod-name`.
- __Key-value type modifier__. The value of a modifier is separated from its name by a single underscore (`_`). The full name is created using the scheme: `block-name__elem-name_mod-name_mod-val`.

```html
<div class="block block--mod">...</div>
<div class="block block--size-big block--shadow-yes">...</div>
```

Use modifier class name as selector:

```css
.block--hidden { }
/* To alter elements based on a block-level modifier: */
.block--mod .block__elem { }
/* Element modifier: */
.block__elem--mod { }
```

To alter elements based on a block-level modifier:

```css
.block--mod .block__elem { }
/* Element modifier: */
.block__elem--mod { }
```

Element modifier:

```css
.block__elem--mod { }
```

## Example

```html
<form class="form form--theme-xmas form--simple">
  <input class="form__input" type="text" />
  <input
    class="form__submit form__submit--disabled"
    type="submit" />
</form>
```

```css
.form { }
.form--theme-xmas { }
.form--simple { }
.form__input { }
.form__submit { }
.form__submit--disabled { }
```
