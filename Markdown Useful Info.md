## Notes on Markdown and HTML

Markdown itself is in some ways limited (as a language) however, because inline HTML works with markdown on GitHub, the use of HTML tags and other HTML syntax, expands the capabilities of markdown greatly.

Therefore, the following hints will use a mix of HTML and markup syntax.

**NOTE:**
It is important to note that within inline HTML syntax, I have sometimes had trouble using markup language when editing .md files on GitHub web - though this has not always been the case. Sometimes, if I have defined a paragraph using `<p> paragraph here </p>` tags, I have not been able to use markup syntax within the `<p>` paragraph tags `</p>`.

Using an IDE might prevent these problems, as I have yet to come across these issues on PyCharm - likely other IDEs also "patch" these issues.

## Code Blocks

#### Using Markup Syntax

`Inline code` can be achieved with `single backticks` (UK keyboard layouts this the key to the left of the 1).

Code blocks can be inserted with triple backticks. The line before the code and the line after the code should be triple backticks. 
```
This is a code block. 

Inline code achieved with single `backticks`.

Programming language can also be specified.
After the backticks, type the language name:
```python ... ``` for example.
```

To escape backticks in your code (have them appear and not intefere with the rest of your .md doc), use double backticks.

`` escape some ` backticks here ``

The above is achieved using:
```markdown
``escape some ` backticks here``
```

#### Using HTML Syntax

For inline code insert your code between `<code>` and `</code>` - this is for one line of code or a single phrase.

For code blocks use `<pre><code>` with code here, then `</code></pre>`.

A useful extra is that you can add line numbers to the code **AND** specify the code language if you use:
```html
<pre class="line-numbers">
    <code class="language-python">
        CODE GOES HERE
    </code>
</pre>
```
To add a language class, always use the syntax `class="language-` followed by the language you want to specify. The following is a list of the language classes supported by HTML's code blocks:

- markup

Use the above for XML and HTML. Continued below:

- css
- clike
- javascript
- java
- php
- scss
- bash
- python
- sql
- https
- csharp
- aspnet
- scala
- haskell
- objectivec
- latex
- git

To be written after the `class="language-` exactly as you see it in the above list.

##### NB: Inserting Code Blocks Within HTML Tables in Markdown

If you make a table using HTML syntax `<table> table here </table>` and want to insert code within one of the cells of the table, you could:

1. Use the `<tr> and </tr>` tags to create a new row
2. Use the `<td> and </td>` tags to insert data in one of the cells of the row
3. Ensure that you have a blank line before the code and a blank link after the backticks that define the code block.
4. Use the triple backticks to write the code block (as you would normally do)

```html
<table>
    <tr>
        <td>
            
            ```language
            code here
            ```
            
        </td>
    </tr>
</table>
```
Though I am unsure why, the blank lines before and after the backticks have been essential in making the code appear as a code block. Whether this is the best/most appropriate way of achieving this, I do not know, however it does work.

## Helpful Little Tips

### Line Breaks and Paragraphs

To specify line breaks use the HTML tag `<br>`. Technically trailing whitespace can be used in markup to denote a single linebreak (two spaces at the end of the first line), however it is not recommended because it is not immediately clear where the line breaks are.

Paragraphs are created when there is a blank line between two sections of text. Alternatively, using HTML tags `<p>` at the start of a paragraph, and `</p` at the end of a paragraph.

##### Code block to demonstrate this:
```
Using blank lines to create paragraphs. This is paragraph 1.

This is paragraph 2.

Using HTML tag to create paragraphs. <p> This is paragraph 1. </p> <p>This is paragraph 2 </p>
```
##### The output of this would be:

Using blank lines to create paragraphs. This is paragraph 1.

Paragraph 2.

Using HTML tag to create paragraphs. <p>This is paragraph 1. </p> <p>This is paragraph 2 </p>

## Create Tables

In Markdown tables can be created using `|` pipe symbols and `-` hyphens.

| Column 1 Header | Column 2 Header |
|-----------------|-----------------|
| Row 1           | Row 1           |
| Row 2           | Row 2           |
| Row 3           | Row 3           |

The syntax for this is simply:
```
|Column 1 Header|Column 2 Header|
|-|-|
|Row 1|Row 1|
|Row 2|Row 2|
|Row 3|Row 3|
```
The above is likely poor practice (spaces before and after pipes is preferable, as is using multiple hyphens to denote headers). However, the point is to show the ease of which a table can be created. The single hyphens are incorrect, however in PyCharm (and other IDEs) this will be autocorrected if the headers are modified (to fit the width).

The `| - | - |` section of the syntax, under the column headers tells markup that the row above is the table headers.

Writing with markdown in PyCharm, edits the table as you type, inserting the appropriate number of hyphens and standardises the column widths.

#### Aligning Columns in Tables

The `:` colon character can be used with the `-` hyphen character to define the alignment of each column of the table.

| left | centre | right | justified                |
|:-----|:------:|------:|--------------------------|
| `:-` | `:-:`  |  `-:` | Not possible in markdown |

### Create Tables with HTML Syntax

HTML tables are created with the following tags:

<table>
    <tr>
        <th>Tag syntax by hierarchy</th>
        <th>Description</th>
    </tr>
    <tr>
        <td>

```html
<table> and </table>
```
</td>
        <td>This creates the table itself</td>
    </tr>
    <tr>
        <td>

```html
<tr> and </tr>
```
</td>
        <td>Table Row - create a new table row</td>
    </tr>
    <tr>
        <td>

```html
<th> and </th>
```

</td>
        <td>
            Table Header - specify the headers for the table
        </td>
    </tr>
    <tr>
        <td>

```html
<td> and </td>
```

</td>
        <td>Table Data - this is where you enter data for the table</td>
    </tr>
    <tr>
        <td>Table headers and table data should be nested between table rows tags.</td>
        <td>Table rows should be nested between the table tags</td>
    </tr>
</table>

```html
<table>
    <tr>
        <th>
            Column Header 1
        </th>
        <th>
            Column Header 2
        </th>
    </tr>
    <tr>
        <td>
            Row 1 Column 1 Data
        </td>
        <td>
            Row 1 Column 2 Data
        </td>
    </tr>
</table>
```

## HTML `<span>` tag

#### Quick Note/Update

GitHub webpage does not seem to handle the `<span>` tag well. Will try the `<div>` tag instead.

#### HTML `<span>` tag

The HTML span tag is used to edit or modify a specific the section within the span tags. In the context of Markdown text, it can be used with `style="..."` the font colour, family, size and other attributes can be modified.

## HTML `style=" "`

### Change Colour of Section of Text

GitHub web does not seem to like the use of span for changing inline text, however for the sake of IDE users who can test this - this is normal coloured text and <span style="color:crimson">this is a colour specific section</span> then back to normal. This is achieved with the use of HTML tag `<span>` and specifying the `style` of the text:
```html
<span style="color:crimson">colour specific section</span>
```

To change the colour of a block of text, the `<div>` tag could be used.

<div style="color:teal">Here is my text in teal.</div>

##### Changing Plain Text Colour in GitHub Web .md files

Using LATEX code in Markdown for GitHub Web.

${\color{red}Red}$

```
${\color{red}Red}$
# The single $ for left-alignment and $$CODE$$ for central
```

Alternative:

${\textsf{\color{lightgreen}Green}}$

```
${\textsf{\color{lightgreen}Green}}$
```

### Change Font Family of Section of Text

The follow table contains "web safe fonts" for CSS and HTML.

| Font Family     | Font Type  |
|-----------------|------------|
| Arial           | sans-serif |
| Verdana         | sans-serif |
| Tahoma          | sans-serif |
| Trebuchet MS    | sans-serif |
| Times New Roman | serif      |
| Georgia         | serif      |
| Garamond        | serif      |
| Courier New     | monospace  |
| Brush Script MT | cursive    |

## Lists

### Markup Syntax

#### Unordered Lists

Unordered lists can be created in Markup by using three symbols:

- A hyphen `-`

* An asterisk `*`

+ A plus sign `+`

Each of these list items were created using the sign they describe - a big "definitely not" usually, don't mix and match your list delimiters, pick one and stick with it.<br>
List items can be indented by using the tab key or preceding the item by spaces.

+ Using the plus sign `+`
  + Using a tab to indent
  + Using two spaces to indent

#### Ordered Lists

Markup will automatically number the lists, therefore the numbers do not have to be in numerical order as you type them, however the first item does need to be preceded by `1.` To indent an item, you can simply tab it or precede it by spaces.

1. Start your list with a `1.` and your first item
   1. Indented item using spaces
2. The next item will numbered automatically.
   1. Indented item using the tab key

### HTML Syntax

#### Unordered Lists

Open the list with the tags `<ul>` and close with `</ul>`. Each list item within the `<ul> </ul>` tags should be enclosed by `<li>` and `</li>` tags. To indent an item on a list, create a list within a list (nest), by using the `<ul>` or `<ol>` tag followed by a `<li>` tag.

`<ul>` = unordered list<br>
`<li>` = list item

<ul>
<li>This is an HTML list, first item.</li>
<li>Second Item.</li>
<ul><li>Unordered indented item</li></ul>
</ul>

The above was created with:
```html
<ul>
    <li>This is an HTML list, first item.</li>
    <li>Second Item.</li>
        <ul>
            <li>Unordered indented item</li>
        </ul>
</ul>
```

#### Ordered Lists

Open the list with the tags `<ol>` and close with `</ol>`. Each list item within the `<ol> </ol>` tags should be enclosed by `<li>` and `</li>` tags. To indent an item on a list, create a list within a list (nest), by using the `<ul>` or `<ol>` tag followed by a `<li>` tag.

`<ol>` = ordered list

<ol>
<li>This is an HTML list, first item.</li>
<ul><li>This is an unordered indented tag</li></ul>
<li>Second Item.</li>
<ol><li>This is an ordered indented tag</li></ol>
</ol>

The above was created with:
```html
<ol>
<li>This is an HTML list, first item.</li>
<ul><li>This is an unordered indented tag</li></ul>
<li>Second Item.</li>
<ol><li>This is an ordered indented tag</li></ol>
</ol>
```
