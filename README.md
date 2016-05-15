# eb-grid

Responsive-grid CSS library that's laser-focused on being easy, super flexible and super fast to build with. Small file size, no style collisions with the major CSS frameworks.


## Another responsive grid: why bother?

eb-grid gives you greater flexibility than other responsive-grid frameworks in two major ways:

**1. Variable column totals:** The primary flaw with other grids is that they require a single, global "base" number of columns for your site, usually 12. Try creating a 5-column row with that; you can't. To have a single base that allows anywhere from 1 to 10 columns, it would have to be a 2,520-column base (Google it). Or, you can use eb-grid's fraction-based class names so you can change the total number of "base" columns for every row of content on your page.

**2. More breakpoints:** eb-grid has 6 distinct breakpoints so you can set different widths for:

  * phones, 
  * phablets, 
  * tablets, 
  * laptops, 
  * desktops, and 
  * widescreen viewports.

Also:

**3. Equal height columns:** Adding one extra class to a row keeps all of its column heights equal, even as their content reflows.

**4. Lightweight:** eb-grid v1.2.0 is just **10 kb minified,** so it won't impact your site's loading time.

**5. No class collisions:** eb-grid **does not interfere** with, and can be used in the same project alongside, other responsive frameworks like Bootstrap and Foundation. So you can use eb-grid as a patch to handle just a certain section, or phase it into a legacy code base, without creating problems in an existing layout.


## Basics

eb-grid has a similar strategy as Bootstrap or Foundation, so if you know how to use those, you'll pick up eb-grid very quickly.

**The main difference is that instead of using a single, global 12- or 16-column grid structure, eb-grid uses fraction-based class names that allow you to set different total column counts for every row of content on your page.**

>Rows of content in eb-grid are given a class name of `.layer` so that developers can use eb-grid in projects without interfering with Bootstrap and Foundation's ".row" class.


### Examples

    <div class="layer">
    
      <div class="col">
        This div will span the full width of the layer in all viewports.
      </div>

      <div class="col phab-1-2">
        This div will span the full width of the layer in viewports up to 480px,
        and will span 1/2 the width of the layer in viewports 481px and above.
      </div>

    </div>
    
Each row of content is created with a div with class `.layer`. Inside it, divs with class `.col` form columns of side-by-side content.

Additional classes can be added to `.col`s to change their widths at certain breakpoints:

    <div class="layer">

      <div class="col ph-3-4 desk-3-7"> blah </div>
      
      <!-- This will be 3/4-width (75%) in viewports less than 1200px,
        and 3/7-width (42.8571%) in viewports 1200px or wider. -->


      <div class="col phab-1-2 tab-2-5"> blah </div>
      
      <!-- This will be full width (100%) in viewports up to 480px,
        1/2-width (50%) in viewports 481px - 767px, and
        2/5-width (40%) in viewports 768px or wider. -->
      
    </div>

Column divs can have as many extra classes as you like. Here's an extreme example:

    <div class="col ph-2-3 phab-3-4 tab-4-5 lap-5-6 desk-6-7 wide-7-8"> Hello </div>
    
This div will span 2/3 of its parent's width by default, 3/4 its width when the viewport is over 480 px wide, 4/5 its width when it's 768+ px wide, 5/6 its width when it's 992+ px wide, 6/7 its width when it's 1200+ px wide, and 7/8 its width when it's 1600+ px wide.

You won't need to set a different fractional width at every single breakpoint like this, but whichever ones you'd like to, you can.


## How to write the class names

**To create a class name for setting a column width, you combine a breakpoint prefix with a fractional-width suffix.** Here are all possible values:


## Breakpoints

<table width="100%">
  <thead>
    <tr>
      <th width="20%">Class prefix</th>
      <th>Viewport size it applies to</th>
      <th>Possible devices targeted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ph-</td>
      <td>0 - 480px</td>
      <td>Phones @ portrait orientation</td>
    </tr>
    <tr>
      <td>phab-</td>
      <td>481px - 767px</td>
      <td>Phablets<br>Phones @ landscape orientation</td>
    </tr>
    <tr>
      <td>tab-</td>
      <td>768px - 991px</td>
      <td>Tablets @ portrait orientation</td>
    </tr>
    <tr>
      <td>lap-</td>
      <td>992px - 1199px</td>
      <td>Smaller laptops<br>Tablets @ landscape orientation</td>
    </tr>
    <tr>
      <td>desk-</td>
      <td>1200px - 1599px</td>
      <td>Most laptop and desktop computers</td>
    </tr>
    <tr>
      <td>wide-</td>
      <td>1600px +</td>
      <td>Large-monitor desktop computers</td>
    </tr>
    <tr>
      <td>print-</td>
      <td>&nbsp;</td>
      <td>Printed pages, regardless of size</td>
    </tr>
  </tbody>
</table>

Note: Since most people probably won't use the `.print-` classes, they can be found in the separate `*-print.css` file in this repo.


## Fractional widths

eb-grid allows you to easily set any fractional width on an element, **up to tenths.** A column really shouldn't need to be narrower than that. Here is a table of all possible column widths, and the class names you can use for them:

<table width="100%">
  <thead>
    <tr>
      <th width="25%">Class suffix</th>
      <th>Width of element in layer</th>
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
      <td>-half<br>-1-2</td>
      <td>50%</td>
    </tr>
    <tr>
      <td>-1-3</td>
      <td>33.3333%</td>
    </tr>
    <tr>
      <td>-2-3</td>
      <td>66.6666%</td>
    </tr>
    <tr>
      <td>-1-4</td>
      <td>25%</td>
    </tr>
    <tr>
      <td>-3-4</td>
      <td>75%</td>
    </tr>
    <tr>
      <td>-1-5</td>
      <td>20%</td>
    </tr>
    <tr>
      <td>-2-5</td>
      <td>40%</td>
    </tr>
    <tr>
      <td>-3-5</td>
      <td>60%</td>
    </tr>
    <tr>
      <td>-4-5</td>
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

Order your columns right-to-left by adding a `.rtl` class to the containing `.layer`:

    <div class="layer rtl">
      <div class="col tab-1-2"> This div will be on the right when it becomes a column at 768px+. </div>
      <div class="col tab-1-2"> This div will be on the left when it becomes a column at 768px+. </div>
    </div>

RTL can also be added at different breakpoints, in case you only want to initiate it at a certain point:

    <div class="layer desk-rtl">
      ...
    </div>

The `.col`s inside this `.layer` will run left to right on viewports less than 1200px, and right to left on viewports 1200px or wider.


## Equal height columns

As of v1.2.0, eb-grid makes it easy to **ensure that all the columns in a layer are the same height** whenever they're side-by-side. Just use the `eq-height` class on the containing `.layer`:

    <div class="layer tab-eq-height">
      <div class="col tab-1-4 lap-1-8">No matter what these columns have in them,</div>
      <div class="col tab-1-4 lap-3-8">they will all have the same height as whichever one is tallest.</div>
      <div class="col tab-1-2 lap-4-8">And since it uses CSS Table display, it'll work in IE8+!</div>
    </div>

You can also combine this with RTL support to make equal height columns that order from right to left:

    <div class="layer lap-eq-height rtl">
      ...
    </div>

**Note:** it's important to include the breakpoint prefixes so you're only adding this class at the breakpoint where your columns are all side-by-side; if they're stacked you might get unexpected results. This has been a major item on the eb-grid wish-list. Create an issue if it's not working right.


## Helper classes

The goal of eb-grid is to be as lean and grid-focused as possible, so the only other things eb-grid tries to handle are visibility, alignment and padding.


### Visibility

Sometimes you need a column to show up or go away at a certain breakpoint. Here's how to do that.

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
      <td>Hides the element by setting it to <code>display:none!important</code>.</td>
    </tr>
    <tr>
      <td>.ph-show</td>
      <td>Shows the element by setting it to <code>display:block!important</code>.</td>
    </tr>
  </tbody>
</table>

**Note: Change `ph-` to another breakpoint prefix** to hide or show the element dynamically at that breakpoint. For example:

    <div class="col ph-hide lap-show lap-1-3">
      This div will be hidden on viewports up to 991px,
      but will be visible on viewports wider than that
      (and 1/3 the width of its parent).
    </div>


### Alignment

You can set the alignment of text and images, or even block elements like `.col`s, with the following classes:

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
      <td>Aligns "inline" content (like text and images) left by setting <code>text-align:left!important</code>.</td>
    </tr>
    <tr>
      <td>.align-r</td>
      <td>Aligns "inline" content (like text and images) right by setting <code>text-align:right!important</code>.</td>
    </tr>
    <tr>
      <td>.align-c</td>
      <td>Aligns "inline" content (like text and images) center by setting <code>text-align:center!important</code>.</td>
    </tr>
    <tr>
      <td>.float-l</td>
      <td>Floats block elements (like <code>col</code>s) left by setting <code>float:left!important</code>.</td>
    </tr>
    <tr>
      <td>.float-r</td>
      <td>Floats block elements (like <code>.col</code>s) right by setting <code>float:right!important</code>.</td>
    </tr>
    <tr>
      <td>.float-c</td>
      <td>Floats block elements (like <code>.col</code>s) in the center of a layer by setting <code>float:none!important; margin-left:auto!important; margin-right:auto!important;</code>.</td>
    </tr>
    <tr>
      <td>.first</td>
      <td>Use this class if the element should always be first (all the way left) in a layer.</td>
    </tr>
    <tr>
      <td>.not-first</td>
      <td>Use this class to undo the <code>.first</code> class at any subsequent (wider) breakpoint.</td>
    </tr>
  </tbody>
</table>

**Note: Add any breakpoint prefix** to any of the above classes to set the element's alignment dynamically at a certain breakpoint. For example:

    <div class="col ph-1-3 desk-align-r desk-1-9">
      Text in this div will be left-aligned (and 1/3 the width of its parent) on viewports up to 1199px,
      but right-aligned (and 1/9 the width of its parent) on viewports wider than that.
    </div>


### Padding ###

By default, there is no padding applied to `.col` and `.layer` (or any other) elements in eb-grid. This gives you more flexibility and prevents interfering with any existing or intended layout you have. If you want to add padding to an element, use custom styling or one of the following:

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
      <td>Sets <code>padding-left:10px; padding-right:10px;</code> on the element. Does NOT set padding on the top and bottom (use <code>.pad-v</code> or <code>.pad-all</code> for that).</td>
    </tr>
    <tr>
      <td>.pad-v</td>
      <td>Sets <code>padding-top:10px; padding-bottom:10px;</code> on the element. Does NOT set padding on the left and right sides (use <code>.pad</code> or <code>.pad-all</code> for that).</td>
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

    <div class="col pad-v phab-pad-all">
      This div will have top and bottom padding on viewports up to 480px,
      and will have top, bottom, left and right padding on viewports wider than that.
    </div>
    

## Get started

- Click the "Download ZIP" button, open it after it downloads.
- Move the `eb-grid-v1.x.x.min.css` file into your website's root directory or its `css/` subdirectory or wherever.
- Add a reference to it in your webpage's `<head>` section, for example: `<link rel="stylesheet" href="css/eb-grid-v1.x.x.min.css">`.
- It's ready to use. Add eb-grid's classes to your HTML elements however you like.


## Support

If you have questions or suggestions about eb-grid, just create an issue. Hope this works for you. Thanks.


## Version 2

FYI, [eb-grid v2.x](https://github.com/ericbutler555/eb-grid/tree/v2) exists in the v2 branch. The main difference is that v2 gives a default 10px padding to all column sides, which is a bit more like Bootstrap or Foundation. Otherwise v1 and v2 are the same. [Check out version 2](https://github.com/ericbutler555/eb-grid/tree/v2) if you're interested.
