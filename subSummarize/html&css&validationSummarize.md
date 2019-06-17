# week 1精炼

## HTML

### 1. Tags
`<!DOCTYPE Tag>` DOCTYPE declaration. What type of document is this (html), what version?  
`<html>` root element.     Highest level element in the document  
`<head>` Document head.  Contains metadata and configuration information  
`<meta charset="UTF-8">` metadata to assist browser.  Tells browser we are using UTF-8 encoding  
`<title>` contains title of webpage.  Tells browser we are using UTF-8 encoding  
`<body>` Document body.  Contains content to be rendered by the browser  
The `<pre>` element is used to preserve whitespace.
`<div>`  Divisions are used as generic containers for other **elements**.
`<span>`Spans are used as generic containers for **text**

#### Tables
Tables are used to display **Tabular data**.
- Defined using a `<table>` tag
- Tables are made up of rows, defined using `<tr>` tags
- Rows are made up of individual cells
- Individual cells can be defined as headings `<th>` or data `<td>`
  e.g. 
  ```html
    <table>
        <tr>
            <th>1st Column</th>
            <th>2nd Column</th>
        </tr>
        <tr>
            <td>Data</td>
            <td>More data</td>
        </tr>
    </table>
  ```
#### Merging cells
Cells can be defined to span more than one row or column
- Use `<colspan>` attribute to have a cell take up more space horizontally
Use `<rowspan>` attribute to have a cell take up more space vertically
```html
<table>
    <tr>
        <th colspan=2>Header</th>
    </tr>
    <tr>
      <td rowspan=2>Data</td>
      <td>More data</td>
    </tr>
    <tr>
        <td>Even more data</td>
    </tr>
</table>
```

### Anchor elements
The a element is used to create hyperlinks.
- Takes a href attribute whose value is the link location
- Content is the text visible to the user
- Other attributes tell the browser how to behave when following the link e.g. _target_
e.g. `<a href="http://google.com">A link to Google</a>`

### Image elements
The img element is used to display images.
- src is the **location of the image**, either on the local machine or somewhere else on the internet.
- alt is the **text to display** if the image cannot load.
e.g. `<img src="local_image.jpg" alt="This text shows if the image can't load">`

### Forms
Forms allow for input and submission of user data.
- Defined using a form tag
- Inputs defined using these tags:
  - input
  - select
  - textarea
  - button
    e.g. 
    ```html
    <form action="/page.php">
        Name:<br />
        <input type="text" name="firstname" value="Bob" />
        <br />
        Occupation:<br />
        <input type="text" name="lastname" value="Anthropologist" />
        <br /><br />
        <input type="submit" value="Submit" />
    </form>
    ```

## 2. Attributes

### id Attributes
>The id attribute is a unique identifier that can be assigned to an individual element in a document.

- Must be unique within that document.
- An element can only have 1 id
- Can be used to link to a subsection of a page.
- Can be used in CSS or when selecting elements in cod (more on this in weeks 2 & 3)
e.g. `<h1 id="first_heading">It's the first heading</h1>`

### class Attribute
> The class attribute is a common identifier that can be assigned to group elements in a document.

- Can be used across different elements of different types.
- An element can have multiple classes.
- Can be used in CSS or when selecting elements in code (more on this in weeks 2 & 3)
e.g. `<p class="main bob">It's Bob's main paragraph</p>`

###style Attribute
> The style attribute is used to change the appearance of an
individual element in a document.

- Same syntax as CSS (more on this next week)
e.g. 
```html
<div style="background-color: grey;">
This div has a grey background
</div>
```

---

## CSS
### CSS定义
> Cascading Style Sheets is a set of layered rules that describe how the elements of a HTML document
should appear.

1. HTML was never designed to hold style information.
2. The introduction of basic style attributes and tags made documents messy and hard-to-maintain.
3. CSS separates the the style information from the elements.
4. CSS allows us to style multiple web pages with a single stylesheet.

### CSS语法syntax
![CSS syntax picture](week2/cssSyntax.PNG)

### CSS的使用
1. External Style Sheet
    Place your CSS in a separate file e.g. style.css  
     ```css
     h1 {
        color: red;
        font-family: 'Noto Sans';
        }
     ```
    Link the stylesheet using a link tag in your document's head:
    ```html
    <head>
        <link rel="stylesheet" type="text/css" href="style.css">
    </head>
    ```
    
2. Internal Style Sheet
    Use a style attribute on the chosen element
    ```html
    <body>
        <h1 style="color: red; font-family: 'Noto Sans';">This is a heading</h1>
    </body>
    ```

### CSS style之间的优先级之分
Rules (applied in this order) :

1. inline css ( html style attribute ) overrides css rules in style tag and css file
2. a more specific selector takes precedence over a less specific one
3. rules that appear later in the code override earlier rules if both have the same specificity.
4. A css rule with !important always takes precedence.

---

##Validation
问：what happens if your website doesn't meet the
standard?
答：Undefined behavior. Which leads to your website looking di

问：怎样确保网页正确显示？
答：

问：为何要进行validation?
答：
1. Validation can help you debug your code.
2. Validation can help future-proof your work.
3. Validation eases maintenance.
