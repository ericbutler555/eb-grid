# Ro - a responsive grid library.

A lean, mobile-first responsive CSS library.

Easy to understand, flexible and helpful. Small file (9kb), works by itself or with other libraries.

Options:

* Up to 6 media breakpoints
* Any # of columns per row, 1-10
* Equal-height columns
* Reverse column ordering

## How to use

Give each row container a `.ro` class.

Give each column a `.col` class. For responsive widths, form class names by combining a breakpoint prefix and a fraction. For example,

    .tab-2-3

will make a column that's 2/3 wide on a tablet (768px or wider).

### Breakpoint prefixes for class names

<table width="100%">
  <thead>
    <tr>
      <th width="20%">Class prefix</th>
      <th>Viewport it applies to</th>
      <th>Devices targeted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.ph-</td>
      <td>0 - 543px</td>
      <td>Phones @ portrait orientation</td>
    </tr>
    <tr>
      <td>.phab-</td>
      <td>544px - 767px</td>
      <td>Phablets, phones @ landscape orientation</td>
    </tr>
    <tr>
      <td>.tab-</td>
      <td>768px - 999px</td>
      <td>Tablets @ portrait orientation</td>
    </tr>
    <tr>
      <td>.md-</td>
      <td>1000px - 1199px</td>
      <td>Tablets @ landscape orientation</td>
    </tr>
    <tr>
      <td>.lap-</td>
      <td>1200px - 1399px</td>
      <td>Laptop computers</td>
    </tr>
    <tr>
      <td>.desk-</td>
      <td>1400px +</td>
      <td>Desktop computers</td>
    </tr>
  </tbody>
</table>

### Fractions for class names

Any fraction up to tenths (1/10, 7/10, etc.) is supported. 4/6 works the same as 2/3. For the class name, use hyphens instead of slashes: `1-4` instead of `1/4`.

Use the `.auto` class to let a column or element stay its natural width.

### Examples

    <div class="ro">

      <div class="col phab-1-2 tab-1-4">
        Full width on phones,
        50% width on phablets,
        25% width on tablets and up.
      </div>

      <div class="col lap-1-2">
        Full width up to 1199px,
        50% width from 1200px up.
      </div>

    </div>

## Helper classes

### Right to left column ordering

Add the `.rtl` class to a row to make its columns order from right to left. For example,

    <div class="ro rtl">
      <div class="col tab-2-3"> ... </div>
      <div class="col tab-1-3"> ... </div>
    </div>

### Equal height columns

Make all the columns in a row the same height by adding the `.eq-height` class at the breakpoint you prefer. For example,

    <div class="ro lap-eq-height">
      <div class="col lap-1-5"> ... </div>
      <div class="col lap-3-5"> ... </div>
      <div class="col lap-1-5"> ... </div>
    </div>

You can also combine this with the `.rtl` class to make equal height columns that order from right to left:

    <div class="ro lap-eq-height lap-rtl"> ... </div>

### Hide and show

To hide or show an element, use a breakpoint prefix with `hide` or `show`:

    <div class="col ph-hide tab-show">
      Will only display on tablets or wider.
    </div>

### Alignment

Set an element's text alignment or float:

* `.align-l` aligns text left
* `.align-r` aligns text right
* `.align-c` centers text

* `.float-l` floats the element left
* `.float-r` floats the element right
* `.float-c` adds margin auto to center the element

Add a breakpoint prefix to any of these to make them viewport-relative. For example,

    <div class="col align-c tab-align-l">
      Text is centered on phones and phablets,
      but left-aligned on tablets and up.
    </div>

### Padding

Rows and columns don't have any default padding. If you want some, add one or more of these classes:

* `.pad` adds 10px of padding to the left and right sides of the element.
* `.pad-v` adds 10px of padding to the top and bottom of the element.
* `.pad-t` adds 10px of top padding.
* `.pad-b` adds 10px of bottom padding.
* `.pad-l` adds 10px of left padding.
* `.pad-r` adds 10px of right padding.

Add a breakpoint prefix to any of these to make them viewport-relative. For example,

    <div class="col tab-pad">
      Only adds 10px of left and right padding on tablets and up.
    </div>

## Get started

* Click the "Download ZIP" button, unzip it after it downloads.
* Move the `ro.min.css` file into your site files.
* Add a reference to it in your webpage's `<head>` section, for example: `<link rel="stylesheet" href="css/ro.min.css">`.
* Add Ro's classes to your page's HTML elements however you like.
