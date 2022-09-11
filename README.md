
# Learn More About CSS Pseudo Selectors By Building A Balance Sheet, Completed

> - You can use CSS pseudo selectors to change specific HTML elements.
> - In this course, you'll build a balance sheet using pseudo selectors. You'll learn how to change the style of an element when you hover over it with your mouse, and trigger other events on your webpage.
---

> **Step 1** <br>
Set up your HTML with the `DOCTYPE`, `html` indicating this document is in English, `head`, and `body` elements.<br>
Give your `head` element the appropriate `meta` elements for the `charset` and `viewport`, a `title` element with an appropriate title, and a `link` element for your stylesheet.

```html
#index.html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Balance Sheet</title>
    <link rel="stylesheet" href="./styles.css">
  </head>
  <body>
  </body>
</html>
```
> **Step 2** <br>
Within your `body` element, nest a `section` element within a `main` element.

```html
#index.html
  <body>
    <main>
      <section>

      </section>
    </main>
  </body>
```
> **Step 3** <br>
Within your `section` element, add an `h1` element with a nested `span` element.

```html
#index.html
      <section>
        <h1>
          <span>
            
          </span>
        </h1>
      </section>
```
> **Step 4** <br>
Screen readers announce HTML elements based on the document flow. We will eventually want the balance sheet to have a heading of "Balance Sheet" and a subheading of "AcmeWidgetCorp". However, this order does not make sense if announced by a screen reader.<br>
Give your existing `span` the `class` attribute set to `flex`, and add two `span` elements within it. Give the first the text `AcmeWidgetCorp`. Give the second the text `Balance Sheet`. You will use CSS to reverse the order of the text on the page, but the HTML order will make more sense for a screen reader.

```html
#index.html
          <span class="flex">
            <span>AcmeWidgetCorp</span>
            <span>Balance Sheet</span>
          </span>
```
> **Step 5** <br>
Below your `h1` element, create a `div` element. Give it an `id` attribute set to `years`. You want this particular element to be hidden from screen readers, so give it the `aria-hidden` attribute set to `true`.

```html
#index.html
        <div id="years" aria-hidden="true">

        </div>
```
> **Step 6** <br>
Within your `div` element, add three `span` elements. Give each of them a `class` attribute set to `year`, and add the following text (in order): `2019`, `2020`, and `2021`.

```html
#index.html
        <div id="years" aria-hidden="true">
          <span class="year">2019</span>
          <span class="year">2020</span>
          <span class="year">2021</span>
        </div>
```
> **Step 7** <br>
Below your existing `div` element, add a new `div` element with a `class` set to `table-wrap`. This will be the container for your tables.<br>
Within that, add three `table` elements. You will be using CSS to style these into a single table, but using separate tables will help screen readers understand the document flow.

```html
#index.html
        <div class="table-wrap">
          <table></table>
          <table></table>
          <table></table>
        </div>
```
> **Step 8** <br>
HTML tables use the `caption` element to describe what the table is about. The `caption` element should always be the first child of a `table`, but can be positioned with the `caption-side` CSS property.<br>
Add a `caption` element to your first `table`, and give it the text `Assets`.

```html
#index.html
          <table>
            <caption>Assets</caption>
          </table>
```
> **Step 9** <br>
The `thead` and `tbody` elements are used to indicate which portion of your table is the header, and which portion contains the primary data or content.<br>
Add a `thead` and `tbody` to your first `table`, below the `caption` element.

```html
#index.html
          <table>
            <caption>Assets</caption>
            <thead></thead>
            <tbody></tbody>
          </table>
```
> **Step 10** <br>
The `tr` element is used to indicate a table row. Add a `tr` element within your `thead` element. In your new `tr` element, add a `td` element, followed by three `th` elements.<br>
The `td` element indicates a data cell, while the `th` element indicates a header cell.

```html
#index.html
            <thead>
              <tr>
                <td></td>
                <th></th>
                <th></th>
                <th></th>
              </tr>
            </thead>
```
> **Step 11** <br>
Within each of your new `th` elements, nest a `span` element with the `class` set to `sr-only year`. Give them the following text (in order): `2019`, `2020`, and `2021`.<br>
Give your third `th` element the `class` attribute set to `current`.<br>
Leave the `td` element empty. This element exists only to ensure your table has a four-column layout and associate the headers with the correct columns.

```html
#index.html
            <thead>
              <tr>
                <td></td>
                <th><span class="sr-only year">2019</span></th>
                <th><span class="sr-only year">2020</span></th>
                <th class="current"><span class="sr-only year">2021</span></th>
              </tr>
            </thead>
```
> **Step 12** <br>
Within your `tbody` element, add four `tr` elements. Give the first three a `class` attribute set to `data`, and the fourth a `class` attribute set to `total`.

```html
#index.html
            <tbody>
              <tr class="data"></tr>
              <tr class="data"></tr>
              <tr class="data"></tr>
              <tr class="total"></tr>
            </tbody>
```
> **Step 13** <br>
In your first `tr`, add a `th` element with the text `Cash This is the cash we currently have on hand.`. Wrap all of that text except `Cash ` in a `span` element with the `class` set to `description`.<br>
Following that, add three `td` elements with the following text (in order): `$25`, `$30`, `$28`. Give the third `td` element a `class` attribute set to `current`.

```html
#index.html
              <tr class="data">
                <th>Cash <span class="description">This is the cash we currently have on hand.</span></th>
                <td>$25</td>
                <td>$30</td>
                <td class="current">$28</td>
              </tr>
```
> **Step 14** <br>
In your second `tr` element, add a `th` element with the text `Checking Our primary transactional account.`. Wrap that text, except for `Checking` , in a `span` element with the `class` attribute set to `description`.<br>
Following that, add three `td` elements with the following text (in order): `$54`, `$56`, `$53`. Give the third `td` element a `class` attribute set to `current`.

```html
#index.html
              <tr class="data">
                <th>Checking <span class="description">Our primary transactional account.</span></th>
                <td>$54</td>
                <td>$56</td>
                <td class="current">$53</td>
              </tr>
```
> **Step 15** <br>
In your third `tr` element, add a `th` element with the text `Savings Funds set aside for emergencies.`. Wrap that text, except for `Savings `, in a `span` element with the `class` attribute set to `description`.<br>
Following that, add three `td` elements with the following text (in order): `$500`, `$650`, `$728`. Give the third `td` element a `class` attribute set to `current`.

```html
#index.html
              <tr class="data">
                <th>Savings <span class="description">Funds set aside for emergencies.</span></th>
                <td>$500</td>
                <td>$650</td>
                <td class="current">$728</td>
              </tr>
```
> **Step 16** <br>
In your fourth `tr` element, add a `th` element with the text `Total Assets`. Wrap the text `Assets` in a `span` element with the `class` attribute set to `sr-only`.<br>
Following that, add three `td` elements with the following text (in order): `$579`, `$736`, `$809`. Give the third `td` element a `class` attribute set to `current`.

```html
#index.html
              <tr class="total">
                <th>Total <span class="sr-only">Assets</span></th>
                <td><span class="sr-only year">$579</span></td>
                <td><span class="sr-only year">$736</span></td>
                <td class="current"><span class="sr-only year">$809</span></td>
              </tr>
```
> **Step 17** <br>
Time to move on to your second table. Start by giving it a `caption` element set to `Liabilities`. Then add your `thead` and `tbody`.

```html
#index.html
          <table>
            <caption>Liabilities</caption>
            <thead></thead>
            <tbody></tbody>
          </table>
```
> **Step 18** <br>
Within your `thead`, add a `tr`. Inside that, add a `td` and three `th` elements.

```html
#index.html
          <table>
            <caption>Liabilities</caption>
            <thead>
              <tr>
                <td></td>
                <th></th>
                <th></th>
                <th></th>
              </tr>
            </thead>
            <tbody>
            </tbody>
          </table>
```
> **Step 19** <br>
Give each `th` element a `span` element with the class set to `sr-only` and the following text, in order: `2019`, `2020`, and `2021`.

```html
#index.html
          <table>
            <caption>Liabilities</caption>
            <thead>
              <tr>
                <td></td>
                <th><span class="sr-only">2019</span></th>
                <th><span class="sr-only">2020</span></th>
                <th><span class="sr-only">2021</span></th>
              </tr>
            </thead>
            <tbody>
            </tbody>
          </table>
```
> **Step 20** <br>
Within the `tbody` element, add four `tr` elements. Give the first three the `class` attribute set to `data`, and the fourth the `class` attribute set to `total`.

```html
#index.html
          <table>
            <caption>Liabilities</caption>
            <thead>
              <tr>
              <td></td>
              <th><span class="sr-only">2019</span></th>
              <th><span class="sr-only">2020</span></th>
              <th><span class="sr-only">2021</span></th>
              </tr>
            </thead>
            <tbody>
              <tr class="data"></tr>
              <tr class="data"></tr>
              <tr class="data"></tr>
              <tr class="total"></tr>
            </tbody>
          </table>
```
> **Step 21** <br>
Within the first `tr`, add a `th` element with the text `Loans The outstanding balance on our startup loan.`. Wrap that text, except for `Loans `, within a `span` element with the `class` set to `description`.<br>
Add three `td` elements below that, and give them the following text, in order: `$500`, `$250`, and `$0`. Give the third `td` element a `class` set to `current`.

```html
#index.html
              <tr class="data">
                <th>Loans <span class="description">The outstanding balance on our startup loan.</span></th>
                <td >$500</td>
                <td>$250</td>
                <td class="current">$0</td>
              </tr>
              <tr class="data">
              </tr>
              <tr class="data">
              </tr>
              <tr class="total">
              </tr>
```
> **Step 22** <br>
Within the second `tr`, add a `th` element with the text `Expenses Annual anticipated expenses, such as payroll.`. Wrap that text, except for `Expenses `, within a `span` element with the `class` set to `description`.<br>
Add three `td` elements below that, and give them the following text, in order: `$200`, `$300`, and `$400`. Give the third `td` element a `class` set to `current`.

```html
#index.html
              <tr class="data">
                <th>Loans <span class="description">The outstanding balance on our startup loan.</span></th>
                <td>$500</td>
                <td>$250</td>
                <td class="current">$0</td>
              </tr>
              <tr class="data">
                <th>Expenses <span class="description">Annual anticipated expenses, such as payroll.</span></th>
                <td>$200</td>
                <td>$300</td>
                <td class="current">$400</td>
              </tr>
              <tr class="data">
              </tr>
              <tr class="total">
              </tr>
```
> **Step 23** <br>
Within the third `tr`, add a `th` element with the text `Credit The outstanding balance on our credit card.`. Wrap that text, except for `Credit `, within a `span` element with the `class` set to `description`.<br>
Add three `td` elements below that, and give them the following text, in order: `$50`, `$50`, and `$75`. Give the third `td` element a `class` set to `current`.

```html
#index.html
              <tr class="data">
                <th>Loans <span class="description">The outstanding balance on our startup loan.</span></th>
                <td>$500</td>
                <td>$250</td>
                <td class="current">$0</td>
              </tr>
              <tr class="data">
                <th>Expenses <span class="description">Annual anticipated expenses, such as payroll.</span></th>
                <td>$200</td>
                <td>$300</td>
                <td class="current">$400</td>
              </tr>
              <tr class="data">
                <th>Credit <span class="description">The outstanding balance on our credit card.</span></th>
                <td>$50</td>
                <td>$50</td>
                <td class="current">$75</td>
              </tr>
              <tr class="total">
              </tr>
```
> **Step 24** <br>
In your fourth `tr` element, add a `th` element with the text `Total Liabilities`. Wrap the text `Liabilities` in a `span` element with the `class` attribute set to `sr-only`.<br>
Following that, add three `td` elements with the following text (in order): `$750`, `$600`, `$475`. Give the third `td` element a `class` attribute set to `current`.

```html
#index.html
              <tr class="data">
                <th>Loans <span class="description">The outstanding balance on our startup loan.</span></th>
                <td>$500</td>
                <td>$250</td>
                <td class="current">$0</td>
              </tr>
              <tr class="data">
                <th>Expenses <span class="description">Annual anticipated expenses, such as payroll.</span></th>
                <td>$200</td>
                <td>$300</td>
                <td class="current">$400</td>
              </tr>
              <tr class="data">
                <th>Credit <span class="description">The outstanding balance on our credit card.</span></th>
                <td>$50</td>
                <td>$50</td>
                <td class="current">$75</td>
              </tr>
              <tr class="total">
                <th>Total <span class="sr-only">Liabilities</span></th>
                <td>$750</td>
                <td>$600</td>
                <td class="current">$475</td>
              </tr>
```
> **Step 25** <br>
For your third table, add a `caption` with the text `Net Worth`, and set up a table header and table body.

```html
#index.html
          <table>
            <caption>Net Worth</caption>
            <thead></thead>
            <tbody></tbody>
          </table>
```
> **Step 26** <br>
Within your `thead`, create a `tr` element. In that, add a `td` and three `th` elements. Within each of the `th` elements, add a `span` element with the `class` set to `sr-only` and the following text, in order: `2019`, `2020`, and `2021`.

```html
#index.html
          <table>
            <caption>Net Worth</caption>
            <thead>
              <tr>
                <td></td>
                <th><span class="sr-only">2019</span></th>
                <th><span class="sr-only">2020</span></th>
                <th><span class="sr-only">2021</span></th>
              </tr>
            </thead>
            <tbody>
            </tbody>
          </table>
```
> **Step 27** <br>
Within the `tbody`, add a `tr` with the `class` set to `total`. In that, add a `th` with the text `Total Net Worth`, and wrap `Net Worth` in a `span` with the `class` set to `sr-only`.<br>
Then add three `td` elements, giving the third a `class` set to `current`, and giving each the following text: `$-171`, `$136`, `$334`.

```html
#index.html
          <table>
            <caption>Net Worth</caption>
            <thead>
              <tr>
              <td></td>
              <th><span class="sr-only">2019</span></th>
              <th><span class="sr-only">2020</span></th>
              <th><span class="sr-only">2021</span></th>
              </tr>
            </thead>
            <tbody>
              <tr class="total">
                <th>Total <span class="sr-only">Net Worth</span></th>
                <td>$-171</td>
                <td>$136</td>
                <td class="current">$334</td>
              </tr>
            </tbody>
          </table>
```
> **Step 28** <br>
Time to style your table. Start by resetting the box model. Create an `html` selector and give it a `box-sizing` property set to `border-box`.

```css
#styles.css
html {
  box-sizing: border-box;
}
```
> **Step 29** <br>
Create a `body` selector and give it a `font-family` property set to `sans-serif` and a `color` set to `#0a0a23`.

```css
#styles.css
body {
  font-family: sans-serif;
  color: #0a0a23;
}
```
> **Step 30** <br>
Before you get too far into your styling, you should make use of the `sr-only` class. You can use CSS to make elements with this class completely hidden from the visual page, but still be announced by screen readers.<br>
The CSS you are about to write is a common set of properties used to ensure elements are completely hidden visually.<br>
The `span[class~="sr-only"]` selector will select any `span` element whose `class` *includes* `sr-only`. Create that selector, and give it a `border` property set to `0`.

```css
#styles.css
span[class~="sr-only"] {
  border: 0;
}
```
> **Step 31** <br>
The CSS `clip` property is used to define the visible portions of an element. Set the `span[class~="sr-only"]` selector to have a `clip` property of `rect(1px, 1px, 1px, 1px)`.<br>
The `clip-path` property determines the shape the `clip` property should take. Set both the `clip-path` and `-webkit-clip-path` properties to the value of `inset(50%)`, forming the clip-path into a rectangle within the element.

```css
#styles.css
span[class~="sr-only"] {
  border: 0;
  clip: rect(1px, 1px, 1px, 1px);
  clip-path: inset(50%);
  -webkit-clip-path: inset(50%);
}
```
> **Step 32** <br>
Now you need to size these elements down. Give your `span[class~="sr-only"]` selector a `width` and `height` property set to `1px`.

```css
#styles.css
span[class~="sr-only"] {
  border: 0;
  clip: rect(1px, 1px, 1px, 1px);
  clip-path: inset(50%);
  -webkit-clip-path: inset(50%);
  width: 1px;
  height: 1px;
}
```
> **Step 33** <br>
To prevent the text content from overflowing, give your `span[class~="sr-only"]` selector an `overflow` property set to `hidden` and a `white-space` property set to `nowrap`.

```css
#styles.css
span[class~="sr-only"] {
  border: 0;
  clip: rect(1px, 1px, 1px, 1px);
  clip-path: inset(50%);
  -webkit-clip-path: inset(50%);
  height: 1px;
  width: 1px;
  overflow: hidden;
  white-space: nowrap;
}
```
> **Step 34** <br>
Finally, you need to take these hidden elements out of the document flow. Give the `span[class~="sr-only"]` selector a `position` property set to `absolute`, a `padding` property set to `0`, and a `margin` property set to `-1px`. This will ensure that not only are they no longer visible, but they are not even within the page view.

```css
#styles.css
span[class~="sr-only"] {
  border: 0;
  clip: rect(1px, 1px, 1px, 1px);
  clip-path: inset(50%);
  -webkit-clip-path: inset(50%);
  height: 1px;
  width: 1px;
  overflow: hidden;
  white-space: nowrap;
  position: absolute;
  padding: 0;
  margin: -1px;
}
```
> **Step 35** <br>
Time to style your table heading. Create an `h1` selector. Give it a `max-width` property set to `37.25rem`, a `margin` property set to `0 auto`, and a `padding` property set to `1.5rem 1.25rem`.

```css
#styles.css
h1 {
  max-width: 37.25rem;
  margin: 0 auto;
  padding: 1.5rem 1.25rem;
}
```
> **Step 36** <br>
Target your flex container with an `h1 .flex` selector. Give it a `display` property set to `flex` to enable the flexbox layout. Then set the `flex-direction` property to `column-reverse` - this will display the nested elements from bottom to top. Finally, set the `gap` property to `1rem` to create some space between the elements.

```css
#styles.css
h1 .flex {
  display: flex;
  flex-direction: column-reverse;
  gap: 1rem;
}
```
> **Step 37** <br>
The `:first-of-type` pseudo-selector is used to target the first element that matches the selector. Create an `h1 .flex span:first-of-type` selector to target the first `span` element in your `.flex` container. Remember that your `span` elements are reversed, visually, so this will appear to be the second element on the page.<br>
Give your new selector a `font-size` property of `0.7em` to make it look like a sub-heading.

```css
#styles.css
h1 .flex span:first-of-type {
  font-size: 0.7em;
}
```
> **Step 38** <br>
The `:last-of-type` pseudo-selector does the exact opposite - it targets the last element that matches the selector. Create an `h1 .flex span:last-of-type` selector to target the last `span` in your flex container, and give it a `font-size` property set to `1.2em` to make it look like a header.

```css
#styles.css
h1 .flex span:last-of-type {
  font-size: 1.2em;
}
```
> **Step 39** <br>
You wrapped your table in a section element - now you can style that to give your table a border. Create a `section` selector, and give it a `max-width` property set to `40rem` for responsive design. Set the `margin` property to `0 auto` to center it, and set the `border` property to `2px solid #d0d0d5`.

```css
#styles.css
section {
  max-width: 40rem;
  margin: 0 auto;
  border: 2px solid #d0d0d5;
}
```
> **Step 40** <br>
The last part of your table heading is your years. Create a `#years` selector, and enable flexbox. Justify the content to the end of the flex direction, and make the element sticky. Fix it to the top of its container with `top: 0`.

```css
#styles.css
#years {
  display: flex;
  justify-content: flex-end;
  position: sticky;
  top: 0;
}
```
> **Step 41** <br>
Now apply some color to your `#years`. Make the text `#fff` and the background `#0a0a23`.

```css
#styles.css
#years {
  display: flex;
  justify-content: flex-end;
  position: sticky;
  top: 0;
  color: #fff;
  background-color: #0a0a23;
}
```
> **Step 42** <br>
The `calc()` function is a CSS function that allows you to calculate a value based on other values. For example, you can use it to calculate the width of the viewport minus the margin of an element:<br>
> ```css
> #styles.css
> .example {
>   margin: 10px;
>   width: calc(100% - 20px);
> }
> ```
> Ensure your years do not get hidden by setting a `z-index` of `999`. Then, give it a `margin` of `0 -2px`, and a `padding` set to `0.5rem calc(1.25rem + 2px) 0.5rem 0`.

```css
#styles.css
#years {
  display: flex;
  justify-content: flex-end;
  position: sticky;
  top: 0;
  background: #0a0a23;
  color: #fff;
  z-index: 999;
  margin: 0 -2px;
  padding: 0.5rem calc(1.25rem + 2px) 0.5rem 0;
}
```
> **Step 43** <br>
Style the text within your `#years` element by creating a `#years span[class]` selector. The `span[class]` syntax will target any `span` element that has a `class` attribute set, regardless of the attribute's value.<br>
Give your new selector a `bold` font, a width of `4.5rem`, and text aligned to the right.

```css
#styles.css
#years span[class] {
  font-weight: bold;
  width: 4.5rem;
  text-align: right; 
}
```
> **Step 44** <br>
You wrapped your tables in a container with the `table-wrap` class. Create a selector for that class, and give it a `padding` set to `0 0.75rem 1.5rem 0.75rem`.

```css
#styles.css
.table-wrap {
  padding: 0 0.75rem 1.5rem 0.75rem;
}
```
> **Step 45** <br>
Before you start diving in to the table itself, `your` span elements are currently bolded. Create a `span:not(.sr-only)` selector and give it a `font-weight` property set to `normal`.<br>
The `:not()` pseudo-selector is used to target all elements that do not match the selector - in this case, any of your `span` elements that do not have the `sr-only` class. This ensures that your earlier rules for the `span[class~="sr-only"]` selector are not overwritten.

```css
#styles.css
span:not(.sr-only) {
  font-weight: normal;
}
```
> **Step 46** <br>
Rather than having to constantly double-check you are not overwriting your earlier properties, you can use the `!important` keyword to ensure these properties are always applied, regardless of order or specificity.<br>
Give each property in your `span[class~="sr-only"]` selector an `!important` keyword. Do not change any of the values.

```css
#styles.css
span[class~="sr-only"] {
  border: 0 !important; 
  clip: rect(1px, 1px, 1px, 1px) !important;
  clip-path: inset(50%) !important;
  -webkit-clip-path: inset(50%) !important;
  height: 1px !important;
  width: 1px !important;
  position: absolute !important;
  overflow: hidden !important;
  white-space: nowrap !important;
  padding: 0 !important;
  margin: -1px !important;
}
```
> **Step 47** <br>
Now that you have added the `!important` keyword, you can remove the `:not(.sr-only)` from your `span` selector.

```css
#styles.css
span {
  font-weight: normal;
}
```
> **Step 48** <br>
Create a `table` selector to target your tables. Set the `border-collapse` property to `collapse`, which will allow cell borders to collapse into a single border, instead of a border around each cell. Also set the `border` property to `0` to hide the borders themselves.

```css
#styles.css
table {
  border-collapse: collapse;
  border: 0;
}
```
> **Step 49** <br>
Ensure your table fills its container with a `width` property set to `100%`, then position it relatively and give it a top margin of `3rem`.

```css
#styles.css
table {
  border-collapse: collapse;
  border: 0;
  width: 100%;
  position: relative;
  margin-top: 3rem;
}
```
> **Step 50** <br>
Next you need to style your `caption` elements to look more like headers. Create a `table caption` selector. Set the text to have a color of `#356eaf`, a size of `1.3em`, and a normal weight.

```css
#styles.css
table caption {
  color: #356eaf;
  font-size: 1.3em;
  font-weight: normal;
}
```
> **Step 51** <br>
Now give the captions an absolute position, and shift them `-2.25rem` from the top and `0.5rem` from the left.

```css
#styles.css
table caption {
  color: #356eaf;
  font-size: 1.3em;
  font-weight: normal;
  position: absolute;
  top: -2.25rem;
  left: 0.5rem;
}
```
> **Step 52** <br>
Create a selector to target your `td` elements within your table body. Give them a width to fill the viewport, with a minimum and maximum of `4rem`. This approach ensures that the width is fixed, whereas setting `width` specifically would allow the elements to shrink to the container (because we are using flexbox).

```css
#styles.css
tbody td {
  width: 100vw;
  min-width: 4rem;
  max-width: 4rem;
}
```
> **Step 53** <br>
Now target the `th` elements within your table body, and give them a width of the entire container, less `12rem`.

```css
#styles.css
tbody th {
  width: calc(100% - 12rem);
}
```
> **Step 54** <br>
The `[attribute="value"]` selector targets any element that has an attribute with a specific value. Create a `tr[class="total"]` selector to target specifically your `tr` elements with the `total` class. Give it a bottom border of `4px double #0a0a23` and make the font bold.

```css
#styles.css
tr[class="total"] {
  border-bottom: 4px double #0a0a23;
  font-weight: bold;
}
```
> **Step 55** <br>
Using the same selector syntax, target the `th` elements within your table rows where the `class` is `total`. Align the text to the left, and give them a padding of `0.5rem 0 0.25rem 0.5rem`.

```css
#styles.css
tr[class="total"] th {
  text-align: left;
  padding: 0.5rem 0 0.25rem 0.5rem;
}
```
> **Step 56** <br>
The key difference between `tr[class="total"]` and `tr.total` is that the first will select `tr` elements where the only class is `total`. The second will select `tr` elements where the class includes total.<br>
In your case, `tr.total` will work. You can use this selector to target all `td` elements within your `.total` rows. Align the text to the right, and give them a padding of `0 0.25rem`.

```css
#styles.css
tr.total td {
  text-align: right;
  padding: 0 0.25rem;
}
```
> **Step 57** <br>
The `:nth-of-type()` pseudo-selector is used to target specific elements based on their order among siblings of the same type. Use this pseudo-selector to target the third `td` element within your `total` table rows. Give it a right padding of `0.5rem`.

```css
#styles.css
tr.total td:nth-of-type(3) {
  padding: 0.5rem;
}
```
> **Step 58** <br>
Give your `tr.total` elements a hover effect that changes the background to `#99c9ff`.

```css
#styles.css
tr.total:hover {
  background-color: #99c9ff;
}
```
> **Step 59** <br>
Select your `td` elements with the `class` value of `current`, and make the font italic.

```css
#styles.css
td.current {
  font-style: italic;
}
```
> **Step 60** <br>
Select the `tr` elements with the `class` set to `data`. Give them a background image of `linear-gradient(to bottom, #dfdfe2 1.845rem, white 1.845rem)`.

```css
#styles.css
tr.data {
  background-image: linear-gradient(to bottom, #dfdfe2 1.845rem, white 1.845rem);
}
```
> **Step 61** <br>
Select the `th` elements within your `tr.data` elements. Align the text to the left, and give them a top padding of `0.3rem` and a left padding of `0.5rem`.

```css
#styles.css
tr.data th {
  text-align: left;
  padding-top: 0.3rem;
  padding-left: 0.5rem;
}
```
> **Step 62** <br>
Create a `tr.data th .description` selector to target the elements with the `class` set to `description` that are within your `th` elements in your `.data` table rows. Give them a block display, make the text italic with a normal weight, and position them with a `padding` set to `1rem 0 0.75rem` and a right margin of `-13.5rem`.

```css
#styles.css
tr.data th .description {
  display: block;
  font-style: italic;
  font-weight: normal;
  padding: 1rem 0 0.75rem;
  margin-right: -13.5rem;
}
```
> **Step 63** <br>
Your `span` elements now all have more specific styling, which means you can remove your `span` rule.

```css
#styles.css
span {
  font-weight: normal;
}

/*Delete all!*/
```
> **Step 64** <br>
Your dollar amounts are currently misaligned. Create a selector to target the `td` elements within your `tr.data` elements. Vertically align the text to the top, horizontally align the text to the right, and set the padding to `0.3rem 0.25rem 0`.

```css
#styles.css
tr.data td {
  vertical-align: top;
  text-align: right;
  padding: 0.3rem 0.25rem 0;
}
```
> **Step 65** <br>
Create another selector for the `td` elements within your `tr.data` element, but specifically select the last one. Give this a right padding of `0.5rem`.<br><br>
With this, your balance sheet is complete!

```css
#styles.css
tr.data td:last-of-type {
  padding-right: 0.5rem;
}
```