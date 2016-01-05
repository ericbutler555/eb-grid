# eb-grid

Responsive-grid CSS library that's laser-focused on being easy, super flexible and super fast to build with. Small footprint, no class collisions with the major CSS frameworks.

*As of version 1.1 eb-grid is stable and will continue to be tested and maintained.*

## Another responsive grid: why bother? ####

eb-grid gives you greater flexibility than other responsive frameworks in two major ways:

**1. Variable column totals:** eb-grid uses fraction-based class names so you can change the total number of "base" columns in your grid for every row of content on your page.

**2. More breakpoints:** eb-grid has 6 distinct breakpoints so you can target phones, phablets, tablets, laptops, desktops, and widescreen viewports.

Also:

**3. Less markup:** With eb-grid there are layers (rows) and columns. No outer "container" elements, no negative margin trickery, and nesting elements is fine. Forms are a breeze. In fact, you don't even need layers or columns if you don't want. You can use the fractional-width class names on any elements you want: divs, text, images, form inputs, buttons, whatever.

**4. Lightweight:** eb-grid v1.1 is just **7.3 kb minified.** So there's basically zero performance impact.

**5. No class collisions:** eb-grid **does not interfere** with, and can be used in the same project alongside, other responsive frameworks like Bootstrap and Foundation (as long as you're using them on separate elements). So you can use eb-grid as a patch to handle just a certain section, or slowly phase it into a legacy code base, without creating problems in an existing layout.


## Basics ##

eb-grid has a similar (but simpler) strategy as Bootstrap or Foundation, so if you know how to use those, you'll pick up eb-grid very quickly.

The main difference is that **instead of using a single, global 12- or 16-column grid structure, eb-grid uses fractions in its class names that allow you to set different total column counts for any/every row of content on your page.**

>Rows of content in eb-grid are given a class name of ".layer" so that developers can use eb-grid in projects without interfering with Bootstrap and Foundation's ".row" class.

### Examples ###

    <div class="layer">

      <div class="col phab-1-2">
        This div will span the full width of the layer at viewports up to 480px,
        and will span 1/2 the width of the layer at viewports 481px and above.
      </div>

    </div>
    
Each row of content is created with a div with class `.layer`. Inside it, divs with class `.col` form columns of side-by-side content.

    <div class="layer">

      <div class="col ph-1-2 tab-2-5"> Something </div>
      
      <div class="col ph-1-2 tab-2-5"> Something else </div>
      
      <div class="col tab-1-5"> Another thing </div>

    </div>

Additional classes can be added to `.col`s to change their widths at certain breakpoints. In this example, on viewports up to 767px wide, divs 1 and 2 will be side-by-side and each span 1/2 the width of the layer, while div 3 spans the full width of the layer underneath them. But on viewports 768px or wider, all 3 divs will be side-by-side in the layer, divs 1 and 2 will each span 2/5 the layer's width, and div 3 will span the remaining 1/5.

Column divs can have as many extra classes as you like. Here's an (extreme) example:

    <div class="col ph-1-2 phab-1-3 tab-1-4 lap-1-5 desk-1-6 wide-1-7"> Hello </div>
    
This div will span 1/2 of its parent `.layer` div's width by default, 1/3 its width when the viewport is over 480 px wide, 1/4 its width when it's 768+ px wide, 1/5 its width when it's 992+ px wide, 1/6 its width when it's 1200+ px wide, and 1/7 its width when it's 1600+ px wide. You won't need to set a different fractional width at every single breakpoint like this, but whichever ones you'd like to, you can.


## Breakpoints ##

<table width="100%">
  <thead>
    <tr>
      <th width="20%">Class prefix</th>
      <th>Viewport size it applies to</th>
      <th>Possible device targeted</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ph-</td>
      <td>0 - 480px</td>
      <td>Phone @ portrait orientation</td>
    </tr>
    <tr>
      <td>phab-</td>
      <td>481px - 767px</td>
      <td>Phone @ landscape orientation<br>Phablet</td>
    </tr>
    <tr>
      <td>tab-</td>
      <td>768px - 991px</td>
      <td>iPad @ portrait orientation</td>
    </tr>
    <tr>
      <td>lap-</td>
      <td>992px - 1199px</td>
      <td>iPad @ landscape orientation</td>
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

Note: Since most people probably won't use the `.print-` classes, they can be found in the separate `*-print.css` file.


## Fractional widths ##

eb-grid allows you to easily set any fractional width on an element, up to eighths. It stops there because an element really shouldn't need to be narrower than that. Here is a table of all possible column widths, and the class names you can use for them:

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
  </tbody>
</table>

So to reinforce the idea, to create a class name, you combine a breakpoint prefix from the first table with a fractional suffix from the second table. Got it? Ok.


## Helper classes ##

The goal of eb-grid is to be as lean as possible, so the only other things eb-grid tries to handle are visibility, alignment and spacing.

### Visibility ###

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

**Note: Change `ph` to another breakpoint prefix** to hide or show the element dynamically at that breakpoint. For example:

    <div class="col ph-hide lap-show">
      This div will be hidden on viewports up to 991px,
      but will be visible on viewports wider than that.
    </div>


### Alignment ###

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
      <td>Floats block elements (like <code>col</code>s) left by setting <code>float:left!important</code>.</td>
    </tr>
    <tr>
      <td>.float-r</td>
      <td>Floats block elements (like <code>.col</code>s) right by setting <code>float:right!important</code>.</td>
    </tr>
    <tr>
      <td>.float-c</td>
      <td>Floats block elements (like <code>.col</code>s) in the center of a layer by setting <code>float:none!important; margin-left:auto; margin-right:auto;</code>.</td>
    </tr>
    <tr>
      <td>.first</td>
      <td>Use this class if the element should always be first (all the way left) in a layer.</td>
    </tr>
    <tr>
      <td>.not-first</td>
      <td>Use this class to undo the <code>.first</code> class at any subsequent breakpoint.</td>
    </tr>
  </tbody>
</table>

**Note: Add any breakpoint prefix** to any of the above classes to set the element's alignment dynamically at a certain breakpoint. For example:

    <div class="col desk-align-r">
      Text in this div will be left-aligned on viewports up to 1199px,
      but right-aligned on viewports wider than that.
    </div>
    

### Padding ###

By default, there is no padding applied to `.col` and `.layer` (or any other) elements in eb-grid. This gives you more flexibility and prevents interfering with any existing or intended layout you have. If you want to add padding to an element, use one of the following:

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
      <td>.pad-all</td>
      <td>Sets <code>padding:10px;</code> on the element, so all sides will have padding.</td>
    </tr>
    <tr>
      <td>.pad-v</td>
      <td>Sets <code>padding-top:10px; padding-bottom:10px;</code> on the element. Does NOT set padding on the left and right sides (use <code>.pad</code> or <code>.pad-all</code> for that).</td>
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
    

### Margins ###

By default, there are no margins applied to `.col` and `.layer` (or any other) elements in eb-grid. If you want to add top and/or bottom margin to an element, use one of the following:

<table width="100%">
  <thead>
    <tr>
      <th width="20%">Class name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.bump</td>
      <td>Sets <code>margin-top:10px; margin-bottom:10px;</code> on the element. Does NOT set margins on the left and right sides.</td>
    </tr>
    <tr>
      <td>.bump-t</td>
      <td>Sets <code>margin-top:10px;</code> on the element. Leaves all other margins as-is (0 by default).</td>
    </tr>
    <tr>
      <td>.bump-b</td>
      <td>Sets <code>margin-bottom:10px;</code> on the element. Leaves all other margins as-is (0 by default).</td>
    </tr>
  </tbody>
</table>

**Note:** Breakpoint prefixes do not exist for margins at this time. I haven't seen a need for it that would justify the extra code/file size.


## Get Started ##

- Click the "Download ZIP" button, open it after it downloads.
- Move the `eb-grid-v1.1.min.css` file into your website's root directory or its `css/` subdirectory or wherever.
- Add a reference to it in your webpage's `<head>` section, like: `<link rel="stylesheet" href="css/eb-grid-v1.1.min.css">`.
- It's ready to use. Add eb-grid classes to your HTML elements however you like.


## Support ##

If you have questions or suggestions about eb-grid, just create an issue. Hope this works for you. Thanks.
