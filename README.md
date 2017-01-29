# Ro - a mobile-first, responsive CSS grid library

The easiest, most flexible responsive CSS grid there is. Small file size, works stand-alone or with other frameworks.


## Another responsive grid: why bother?

Ro gives you greater flexibility than other responsive-grid frameworks in several major ways:

**1. More column widths:** Instead of using a global "base" number of columns (usually 12), Ro lets you use any fraction up to tenths to set the width of each column, at each breakpoint and for every row on your page. Create 5 or 7 or 10 equal columns effortlessly.

**2. More breakpoints:** Ro has 6 distinct breakpoints so you can customize content settings for:

  * phones,
  * phablets,
  * tablets,
  * wide (landscape) tablets,
  * laptops, and
  * desktop displays.

**3. Equal height columns:** Add a single class to a row and every column becomes the same height, even as their content reflows.

**4. Flow columns left or right:** Add a single class to a row and its columns order from right to left, at any breakpoint.

**5. Lightweight:** Ro is just **10 kb minified (1.9 kb gzipped),** so it won't impact your site's load time.

**6. No class collisions:** Ro does not interfere with, and can be used in the same project alongside, other responsive frameworks like Bootstrap and Foundation. So you can use Ro as a patch to handle a certain section, or phase it into a legacy site, without impacting the existing layout.


## Basics

Ro uses classes to establish rows, columns, dynamic widths, and other grid-related styling. If you've used [Bootstrap](http://getbootstrap.com/) or [Foundation](http://foundation.zurb.com/sites.html), then Ro will be a breeze.

**The major difference is that instead of using a single, global 12-column "base" structure, Ro uses fraction-based class names so you can set different total column counts for every row of content on your page.**

You also don't need an all-encompassing `.container` -- Ro just needs rows and columns.

>Rows use the `.ro` class name so that developers can use Ro in projects without interfering with other frameworks's `.row` class.


### Examples

    <div class="ro">
    
      <div class="col">
        This div will span the full width of the row in all viewports.
      </div>

      <div class="col phab-1-2">
        This div will span the full width of the row in viewports up to 575px,
        and will span 1/2 the width of the row in viewports 576px and above.
      </div>

    </div>
    
Each row of content is created with a div with class `.ro`. Inside it, divs with class `.col` form columns of side-by-side content.

Additional classes can be added to `.col`s to change their widths at certain breakpoints:

    <div class="ro">

      <div class="col ph-3-4 lap-3-7"> blah </div>
      
      <!-- This will be 3/4-width (75%) in viewports up to 1199px,
        and 3/7-width (42.8571%) in viewports 1200px or wider. -->


      <div class="col phab-1-2 tab-2-5"> blah </div>
      
      <!-- This will be full width (100%) in viewports up to 575px,
        1/2-width (50%) in viewports 576px - 767px, and
        2/5-width (40%) in viewports 768px or wider. -->
      
    </div>

Column divs can have as many extra classes as you like. Here's the most extreme example:

    <div class="col ph-2-3 phab-3-4 tab-4-5 tabw-5-6 lap-6-7 desk-7-8"> Hello </div>
    
This div will span 2/3 of its parent's width by default, 3/4 its width when the viewport is 576+ px wide, 4/5 its width at 768+ px wide, 5/6 its width at 992+ px wide, 6/7 its width at 1200+ px wide, and 7/8 its width at 1600+ px wide.

Obviously you won't need to set a different width at every single breakpoint like this, but for whichever ones you'd like to, you can.


## How to write the class names

**To create a class name for setting a column width, you combine a breakpoint prefix with a fractional-width suffix.** Here are the possible values:


## Breakpoints

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
      <td>ph-</td>
      <td>0 - 575px</td>
      <td>Phones @ portrait orientation</td>
    </tr>
    <tr>
      <td>phab-</td>
      <td>576px - 767px</td>
      <td>Phablets, Phones @ landscape orientation</td>
    </tr>
    <tr>
      <td>tab-</td>
      <td>768px - 991px</td>
      <td>Tablets @ portrait orientation</td>
    </tr>
    <tr>
      <td>tabw-</td>
      <td>992px - 1199px</td>
      <td>Tablets @ landscape orientation</td>
    </tr>
    <tr>
      <td>lap-</td>
      <td>1200px - 1599px</td>
      <td>Most laptop computers</td>
    </tr>
    <tr>
      <td>desk-</td>
      <td>1600px +</td>
      <td>Most desktop computers</td>
    </tr>
  </tbody>
</table>


## Fractional widths

Ro allows you to easily set any fractional width on an element **up to tenths** -- a column really shouldn't need to be narrower than that. Here is a table of all possible column widths, and the class names you can use for them:

<table width="100%">
  <thead>
    <tr>
      <th width="25%">Class suffix</th>
      <th>Width of element in row</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>-full</td>
      <td>100%</td>
    </tr>
    <tr>
      <td>-auto</td>
      <td>its auto/default size</td>
    </tr>
    <tr>
      <td>-half<br>-1-2<br>-2-4<br>-3-6<br>-4-8<br>-5-10</td>
      <td>50%</td>
    </tr>
    <tr>
      <td>-1-3<br>-2-6<br>-3-9</td>
      <td>33.3333%</td>
    </tr>
    <tr>
      <td>-2-3<br>-4-6<br>-6-9</td>
      <td>66.6666%</td>
    </tr>
    <tr>
      <td>-1-4<br>-2-8</td>
      <td>25%</td>
    </tr>
    <tr>
      <td>-3-4<br>-6-8</td>
      <td>75%</td>
    </tr>
    <tr>
      <td>-1-5<br>-2-10</td>
      <td>20%</td>
    </tr>
    <tr>
      <td>-2-5<br>-4-10</td>
      <td>40%</td>
    </tr>
    <tr>
      <td>-3-5<br>-6-10</td>
      <td>60%</td>
    </tr>
    <tr>
      <td>-4-5<br>-8-10</td>
      <td>80%</td>
    </tr>
    <tr>
      <td>-1-6</td>
      <td>16.6666%</td>
    </tr>
    <tr>
      <td>-5-6</td>
      <td>83.3333%</td>
    </tr>
    <tr>
      <td>-1-7</td>
      <td>14.2857%</td>
    </tr>
    <tr>
      <td>-2-7</td>
      <td>28.5714%</td>
    </tr>
    <tr>
      <td>-3-7</td>
      <td>42.8571%</td>
    </tr>
    <tr>
      <td>-4-7</td>
      <td>57.1428%</td>
    </tr>
    <tr>
      <td>-5-7</td>
      <td>71.4285%</td>
    </tr>
    <tr>
      <td>-6-7</td>
      <td>85.7142%</td>
    </tr>
    <tr>
      <td>-1-8</td>
      <td>12.5%</td>
    </tr>
    <tr>
      <td>-3-8</td>
      <td>37.5%</td>
    </tr>
    <tr>
      <td>-5-8</td>
      <td>62.5%</td>
    </tr>
    <tr>
      <td>-7-8</td>
      <td>87.5%</td>
    </tr>
    <tr>
      <td>-1-9</td>
      <td>11.1111%</td>
    </tr>
    <tr>
      <td>-2-9</td>
      <td>22.2222%</td>
    </tr>
    <tr>
      <td>-4-9</td>
      <td>44.4444%</td>
    </tr>
    <tr>
      <td>-5-9</td>
      <td>55.5555%</td>
    </tr>
    <tr>
      <td>-7-9</td>
      <td>77.7777%</td>
    </tr>
    <tr>
      <td>-8-9</td>
      <td>88.8888%</td>
    </tr>
    <tr>
      <td>-1-10</td>
      <td>10%</td>
    </tr>
    <tr>
      <td>-3-10</td>
      <td>30%</td>
    </tr>
    <tr>
      <td>-7-10</td>
      <td>70%</td>
    </tr>
    <tr>
      <td>-9-10</td>
      <td>90%</td>
    </tr>
  </tbody>
</table>


## Right to left (RTL) support

Order your columns right-to-left by adding a `.rtl` class to the containing row:

    <div class="ro rtl">
      <div class="col tab-1-2"> This div will be on the right when it becomes a column at 768px+. </div>
      <div class="col tab-1-2"> This div will be on the left when it becomes a column at 768px+. </div>
    </div>

RTL can also be added at different breakpoints, in case you only want to initiate it at a certain point:

    <div class="ro lap-rtl">
      ...
    </div>

The `.col`s inside this row will run left to right on viewports up to 1199px, and right to left on viewports 1200px or wider.


## Equal height columns

Make all the columns in a row the same height by adding the `.eq-height` class to the containing row:

    <div class="ro tab-eq-height">
      <div class="col tab-1-4 lap-1-8">No matter what these columns have in them,</div>
      <div class="col tab-1-4 lap-3-8">they will all have the same height as whichever one is tallest.</div>
      <div class="col tab-1-2 lap-4-8">And since it uses CSS Table display, it'll work in IE8+!</div>
    </div>

You can also combine this with RTL support to make equal height columns that order from right to left:

    <div class="ro lap-eq-height rtl">
      ...
    </div>

**Note:** it's important to add a breakpoint prefix to `-eq-height` so you're only adding this class at the breakpoint where your column divs sit side-by-side; if they're stacked you may get odd results.


## Helper classes

The goal of Ro is to be as lean and grid-focused as possible, so the only other things it offers helpers for are visibility, alignment, and padding.


### Visibility

Sometimes you need a column to show up or go away at a certain breakpoint. Here's how to do that:

<table width="100%">
  <thead>
    <tr>
      <th width="20%">Class name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.ph-hide</td>
      <td>Hides the element by setting it to <code>display:none</code>.</td>
    </tr>
    <tr>
      <td>.ph-show</td>
      <td>Shows the element by setting it to <code>display:block</code>.</td>
    </tr>
  </tbody>
</table>

**Note: Change `ph-` to another breakpoint prefix** to hide or show the element dynamically at that breakpoint. For example:

    <div class="col ph-hide tabw-show tabw-1-3">
      This div will be hidden on viewports up to 991px,
      but will be visible on viewports wider than that
      (and 1/3 the width of its parent).
    </div>


### Alignment

You can set an element's alignment and float with the following classes:

<table width="100%">
  <thead>
    <tr>
      <th width="20%">Class name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.align-l</td>
      <td>Aligns "inline" content (like text and images) left by setting <code>text-align:left</code>.</td>
    </tr>
    <tr>
      <td>.align-r</td>
      <td>Aligns "inline" content (like text and images) right by setting <code>text-align:right</code>.</td>
    </tr>
    <tr>
      <td>.align-c</td>
      <td>Aligns "inline" content (like text and images) center by setting <code>text-align:center</code>.</td>
    </tr>
    <tr>
      <td>.float-l</td>
      <td>Floats block elements (like divs) left by setting <code>float:left</code>.</td>
    </tr>
    <tr>
      <td>.float-r</td>
      <td>Floats block elements (like divs) right by setting <code>float:right</code>.</td>
    </tr>
    <tr>
      <td>.float-c</td>
      <td>Floats block elements (like divs) in the center of a layer by setting <code>float:none; margin-left:auto; margin-right:auto;</code>.</td>
    </tr>
    <tr>
      <td>.first</td>
      <td>Use this class if an element should always be first (all the way left) in a layer.</td>
    </tr>
    <tr>
      <td>.not-first</td>
      <td>Use this class to undo the <code>.first</code> class at any subsequent (wider) breakpoint.</td>
    </tr>
  </tbody>
</table>

**Note: Add any breakpoint prefix** to any of the above classes to set the element's alignment dynamically at a certain breakpoint. For example:

    <div class="col ph-1-3 lap-1-9 lap-align-r">
      Text in this div will be left-aligned (and 1/3 the width of its parent) on viewports up to 1199px,
      but right-aligned (and 1/9 the width of its parent) on viewports wider than that.
    </div>


### Padding ###

By default, there are no padding styles applied to `.ro` or `.col` (or any other) elements in Ro. This gives you more flexibility and prevents interfering with any existing or intended layout you have. If you want to add padding to an element, use custom styling or one of the following:

<table width="100%">
  <thead>
    <tr>
      <th width="20%">Class name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.pad</td>
      <td>Sets <code>padding-left:10px; padding-right:10px;</code> on the element. Does NOT set padding on the top or bottom (use <code>.pad-v</code> or <code>.pad-all</code> for that).</td>
    </tr>
    <tr>
      <td>.pad-v</td>
      <td>Sets <code>padding-top:10px; padding-bottom:10px;</code> on the element. Does NOT set padding on the left or right sides (use <code>.pad</code> or <code>.pad-all</code> for that).</td>
    </tr>
    <tr>
      <td>.pad-all</td>
      <td>Sets <code>padding:10px;</code> on the element, so all sides will have padding.</td>
    </tr>
    <tr>
      <td>.pad-l</td>
      <td>Sets <code>padding-left:10px;</code> on the element. Leaves all other sides as-is (0 by default).</td>
    </tr>
    <tr>
      <td>.pad-r</td>
      <td>Sets <code>padding-right:10px;</code> on the element. Leaves all other sides as-is (0 by default).</td>
    </tr>
    <tr>
      <td>.pad-t</td>
      <td>Sets <code>padding-top:10px;</code> on the element. Leaves all other sides as-is (0 by default).</td>
    </tr>
    <tr>
      <td>.pad-b</td>
      <td>Sets <code>padding-bottom:10px;</code> on the element. Leaves all other sides as-is (0 by default).</td>
    </tr>
  </tbody>
</table>

**Note: Add any breakpoint prefix** to any of the above classes to set padding dynamically at a certain breakpoint. For example:

    <div class="col pad phab-pad-all">
      This div will have left and right padding on viewports up to 575px,
      and padding on all sides on viewports wider than that.
    </div>
    

## Get started

- Click the "Download ZIP" button, open it after it downloads.
- Move the `ro.min.css` file into your website's `css/` folder or wherever.
- Add a reference to it in your webpage's `<head>` section, for example: `<link rel="stylesheet" href="css/ro.min.css">`.
- It's ready to use. Add Ro's classes to your HTML elements however you like.


## Support

If you have a question or suggestion about Ro, just create an issue. Hope this works for you.
