### 我的回答：
#### HTML
##### Tags
`<!DOCTYPE Tag>` DOCTYPE declaration  
What type of document is this (html), what version?  
`<html>` root element  
Highest level element in the document  
`<head>` Document head  
Contains metadata and configuration information  
`<meta charset="UTF-8">` metadata to assist browser  
Tells browser we are using UTF-8 encoding  
`<title>` contains title of webpage  
Tells browser we are using UTF-8 encoding  
`<body>` Document body  
Contains content to be rendered by the browser  
The `<pre>` element is used to preserve whitespace.  

###### Tables
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
###### Merging cells
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





_Elements can be nested_

All opening/start tags must have a acomanying closing tag, but there are exceptions. eg: br /      hr  

##### Attributes

###### Anchor elements
The a element is used to create hyperlinks.
- Takes a href attribute whose value is the link location
- Content is the text visible to the user
- Other attributes tell the browser how to behave when following the link e.g. _target_
e.g. `<a href="http://google.com">A link to Google</a>`

###### Image elements
The img element is used to display images.
- src is the **location of the image**, either on the local machine or somewhere else on the internet.
- alt is the **text to display** if the image cannot load.
e.g. `<img src="local_image.jpg" alt="This text shows if the image can't load">`
###### Forms
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
#### CSS

