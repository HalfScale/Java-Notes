# CSS Basics

### Syntax

```css
selector{
  property: value;
}
```

### Sample 

- Basic selector
```css
/*Type selector - less sepcific*/
body {
  background-color: blue;
}

/*Class selector - more specific than element selector*/
.sample-class {
  margin: 5px;
  height: 100px;
  width: 100px;
}

/*Id selector - most specific selector*/
#sample-id {
  color: red;
  background-color: black;
}
```

- Advance selector
```css
/*Star selector - Selects every element in the page*/
* {
  border: 1px solid purple;
}

/*Descendant selctor - Selects the inner part of the elements*/
ul li a {
  color: yellow;
}

/*Adjacent selector - Selects the element next to it*/
h4 + ul {
  border: 2px solid black;
}

/*Attribute selector - Selects the element with the specified attribute*/
a[href='www.facebook.com'] {
  text-decoration: none;
}

/*nth of type selector - Selects the element based on the parameter that is passed*/
ul:nth-of-type(3) {
  background: purple; /*only the third 'ul' element in the document will be affected*/
}
```
