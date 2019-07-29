# Inheritance and Cascade in CSS

## Cascade
- CSS is an abbreviation for Cascading Style Sheets, which indicates that the notion of the cascade is important. At its most basic level, it indicates that the order of CSS rules matter, but it's more complex than that.

What selectors win out in the cascade depends on three factors:
- Importance
- Specificity
- Source order

### Importance
In CSS, there is a special piece of syntax you can use to make sure that a 
certain declaration will always win over all others: **!important**.

```html
<p class="better">This is a paragraph.</p>
<p class="better" id="winning">One selector to rule them all!</p>
```
```css
#winning {
  background-color: red;
  border: 1px solid black;
}

.better {
  background-color: gray;
  border: none !important;
}

p {
  background-color: blue;
  color: white;
  padding: 5px;
}
```
- This will result into elements not having any border, even if theres an id specifying
an element, which is the highest in the heirarchy.

### Specificity
- is basically a measure of how specific a selector is — how many elements it could match.

**Heirarchy of specificity:**
> !important > id > class > element

### Source order
- As mentioned above, if multiple competing selectors have the same importance and specificity, the third factor that comes into play to help decide which rule 
wins is source order — later rules will win over earlier rules.

Example:
```css
p {
  color: blue;
}

/*This rule will win over the first one.*/
p{
  color: red;
}
```
