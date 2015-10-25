# eb-grid
Responsive-grid CSS library that's laser-focused and more flexible than Bootstrap or Foundation. Tiny footprint, no class collisions.

*eb-grid is still a work in progress.*

#### Why Bother? ####

eb-grid gives you greater flexibility than other responsive frameworks in two ways:

**More breakpoints:** eb-grid has 6 distinct breakpoints so you can target phones, phablets, tablets, laptops, desktops, and widescreen viewports.

**Variable column totals:** eb-grid uses fraction-based class names so you can change the total number of "base" columns in your grid for every row of content on your page.

**Tiny footprint:** eb-grid is currently just **6.9 kb minified, and just 1.5 kb gzipped.** So there's basically zero performance impact.

**No class collisions:** eb-grid **does not interfere** with, and can be used in the same project alongside, other responsive frameworks like Bootstrap and Foundation (as long as you're using them on separate elements). So you can use eb-grid as a patch to handle just a certain section, or slowly phase it into a legacy code base, without creating problems in an existing layout.


## Basics ##

eb-grid has a similar (but simpler) strategy as Bootstrap or Foundation, so if you know how to use those, you'll pick up eb-grid very quickly.

The main difference is that **instead of using a single, global 12- or 16-column grid structure, eb-grid uses fractions in its class names that allow you to set different total column counts for every row of content.**

>Rows of content in eb-grid are given a class name of ".layer" so that developers can use eb-grid in projects without interfering with Bootstrap and Foundation's ".row" class.

### Basic Examples ###

    <div class="layer">

      <div class="col tab-1-2">
        This div will span the full width of the layer at viewports under 768px,
        and will span 1/2 the width of the layer at viewports 768px and above.
      </div>

      <div class="col tab-2-5">
        This div will span the full width of the layer at viewports under 768px,
        and will span 2/5 the width of the layer at viewports 768px and above.
      </div>

    </div>

Each row of content is created with a div with class `.layer`. Inside it, divs with class `.col` form columns of side-by-side content.

Additional classes can be added to `.col`s to set their widths at certain breakpoints. In this example, `.tab-` signifies that the rule will apply to viewports 992px and above. The `-1-2` and `-2-5` portions of the class names signify that at this viewport width, the divs should be 1/2 and 2/5 the width of their parent `.layer` div, respectively.

Column divs can have as many extra classes as you like. Here's an (extreme) example:

    <div class="col ph-1-2 phab-1-3 tab-1-4 lap-1-5 desk-1-6 wide-1-7">
    
This div will span 1/2 of its parent `.layer` div's width by default, 1/3 its width when the viewport is over 480px wide, 1/4 its width when it's over 768px wide, 1/5 its width when it's over 992px wide, 1/6 its width when it's over 1200px wide, and 1/7 its width when it's over 1600px wide. You probably won't need to set a different fractional width at every single breakpoint, but whichever ones you do need to, you can.


## Breakpoints ##

<table width="100%">
  <thead>
    <tr>
      <th width="15%">Class prefix</th>
      <th>Viewport size it applies to</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.ph-</td>
      <td>0 - 480px</td>
    </tr>
    <tr>
      <td>.phab-</td>
      <td>481px - 767px</td>
    </tr>
    <tr>
      <td>.tab-</td>
      <td>768px - 991px</td>
    </tr>
    <tr>
      <td>.lap-</td>
      <td>992px - 1199px</td>
    </tr>
    <tr>
      <td>.desk-</td>
      <td>1200px - 1599px</td>
    </tr>
    <tr>
      <td>.wide-</td>
      <td>1600px +</td>
    </tr>
    <tr>
      <td>.print-</td>
      <td>Printed pages, regardless of size</td>
    </tr>
  </tbody>
</table>

Note: Since most people probably won't use the `.print-` classes, they can be found in the separate `eb-grid-print.css` file.


## Fractional widths ##

eb-grid allows you to easily set any fractional width on an element, up to eighths. It stops there because an element really shouldn't need to be narrower than that. Here is a table of all possible column widths, and the class names you can use for them:

<table width="100%">
  <thead>
    <tr>
      <th width="15%">Class suffix</th>
      <th>Optional stand-alone class name(s)</th>
      <th>Width of element in layer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>-full</td>
      <td>.full</td>
      <td>100%</td>
    </tr>
    <tr>
      <td>-auto</td>
      <td>.auto</td>
      <td>its auto/default size</td>
    </tr>
    <tr>
      <td>-1-2</td>
      <td>.half, .one-half</td>
      <td>50%</td>
    </tr>
    <tr>
      <td>-1-3</td>
      <td>.third, .one-third</td>
      <td>33.3333%</td>
    </tr>
    <tr>
      <td>-2-3</td>
      <td>.two-thirds</td>
      <td>66.6666%</td>
    </tr>
    
    <tr>
      <td>-1-4</td>
      <td>.fourth, .one-fourth</td>
      <td>25%</td>
    </tr>
    <tr>
      <td>-3-4</td>
      <td>.three-fourths</td>
      <td>75%</td>
    </tr>
    <tr>
      <td>-1-5</td>
      <td>.fifth, .one-fifth</td>
      <td>20%</td>
    </tr>
    <tr>
      <td>-2-5</td>
      <td>.two-fifths</td>
      <td>40%</td>
    </tr>
    <tr>
      <td>-3-5</td>
      <td>.three-fifths</td>
      <td>60%</td>
    </tr>
    <tr>
      <td>-4-5</td>
      <td>.four-fifths</td>
      <td>80%</td>
    </tr>
    <tr>
      <td>-1-6</td>
      <td>.sixth, .one-sixth</td>
      <td>16.6666%</td>
    </tr>
    <tr>
      <td>-5-6</td>
      <td>.five-sixths</td>
      <td>83.3333%</td>
    </tr>
    <tr>
      <td>-1-7</td>
      <td>.seventh, .one-seventh</td>
      <td>14.2857%</td>
    </tr>
    <tr>
      <td>-2-7</td>
      <td>.two-sevenths</td>
      <td>28.5714%</td>
    </tr>
    <tr>
      <td>-3-7</td>
      <td>.three-sevenths</td>
      <td>42.8571%</td>
    </tr>
    <tr>
      <td>-4-7</td>
      <td>.four-sevenths</td>
      <td>57.1428%</td>
    </tr>
    <tr>
      <td>-5-7</td>
      <td>.five-sevenths</td>
      <td>71.4285%</td>
    </tr>
    <tr>
      <td>-6-7</td>
      <td>.six-sevenths</td>
      <td>85.7142%</td>
    </tr>
    <tr>
      <td>-1-8</td>
      <td>.eighth, .one-eighth</td>
      <td>12.5%</td>
    </tr>
    <tr>
      <td>-3-8</td>
      <td>.three-eighths</td>
      <td>37.5%</td>
    </tr>
    <tr>
      <td>-5-8</td>
      <td>.five-eighths</td>
      <td>62.5%</td>
    </tr>
    <tr>
      <td>-7-8</td>
      <td>.seven-eighths</td>
      <td>87.5%</td>
    </tr>
  </tbody>
</table>

Notice the "optional stand-alone class names" in the table above? Those are optional ways of writing a class name for the `.ph-` breakpoint. Since eb-grid takes a mobile-first approach, the `.ph-` breakpoint is the default breakpoint, so if you only apply a width at the `.ph-` level, it will apply to the `.col` at every viewport size. For example:

    <div class="col ph-1-2"></div>
    <div class="col ph-1-4"></div>

is the same as:

    <div class="col half"></div>
    <div class="col one-fourth"></div>

This alternate syntax exists just in case you find it easier to understand that these columns will be 1/2 and 1/4 of the `.layer`'s width at all viewport sizes. You can write it either way; they do the same thing.


## Helper classes ##

The goal of eb-grid is to be as lean as possible, so the only other things eb-grid tries to handle are visibility, alignment and spacing.

#### Visibility ####

Sometimes you need a column to show up or go away at a certain breakpoint. Here's how to do that.

<table width="100%">
  <thead>
    <tr>
      <th width="15%">Class name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.hide</td>
      <td>Hides the element by setting it to <code>display: none</code>.</td>
    </tr>
    <tr>
      <td>.show</td>
      <td>Shows the element by setting it to <code>display: block</code>.</td>
    </tr>
  </tbody>
</table>

**Note:** Add a breakpoint prefix to either of the above visibility classes in order to hide or show a `.col` dynamically at a certain breakpoint. For example, `class="col ph-hide lap-show"` will hide the element on viewports up to 991px, but show it on viewports wider than that.

#### Alignment ####

You can set the alignment of text and images, or even block elements like `.col`s, with the following classes:

<table width="100%">
  <thead>
    <tr>
      <th width="15%">Class name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.align-l</td>
      <td>Aligns "inline" content (like text and images) left.</td>
    </tr>
    <tr>
      <td>.align-r</td>
      <td>Aligns "inline" content (like text and images) right.</td>
    </tr>
    <tr>
      <td>.align-c</td>
      <td>Aligns "inline" content (like text and images) center.</td>
    </tr>
    <tr>
      <td>.align-col-l</td>
      <td>Floats block elements (like <code>col</code>s) left.</td>
    </tr>
    <tr>
      <td>.align-col-r</td>
      <td>Floats block elements (like <code>.col</code>s) right.</td>
    </tr>
    <tr>
      <td>.align-col-c</td>
      <td>Floats block elements (like <code>.col</code>s) in the center of a layer.</td>
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

**Note:** Add a breakpoint prefix to any of the above classes to set the element's alignment dynamically at a certain breakpoint. For example, text in a div with `class="col desk-align-r"` would be left-aligned on viewports up to 1199px, but right-aligned on viewports wider than that.

#### Padding ####

By default, there is no padding applied to `.col` and `.layer` elements in eb-grid. This gives you more flexibility and prevents interfering with any existing or intended layout you have. If you want to add padding to an element, use one of the following:

<table width="100%">
  <thead>
    <tr>
      <th width="15%">Class name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.pad</td>
      <td>Sets 10px of padding on the left and right sides of the element. Does NOT set padding on the top and bottom (use <code>.pad-v</code> or <code>.pad-all</code> for that).</td>
    </tr>
    <tr>
      <td>.pad-all</td>
      <td>Sets 10px of padding on all sides of the element.</td>
    </tr>
    <tr>
      <td>.pad-v</td>
      <td>Sets 10px of padding on the top and bottom sides of the element. Does NOT set padding on the left and right sides (use <code>.pad</code> or <code>.pad-all</code> for that).</td>
    </tr>
    <tr>
      <td>.pad-l</td>
      <td>Sets 10px of padding on the left side of the element. Leaves all other sides as-is (0 by default).</td>
    </tr>
    <tr>
      <td>.pad-r</td>
      <td>Sets 10px of padding on the right side of the element. Leaves all other sides as-is (0 by default).</td>
    </tr>
    <tr>
      <td>.pad-t</td>
      <td>Sets 10px of padding on the top side of the element. Leaves all other sides as-is (0 by default).</td>
    </tr>
    <tr>
      <td>.pad-b</td>
      <td>Sets 10px of padding on the bottom side of the element. Leaves all other sides as-is (0 by default).</td>
    </tr>
  </tbody>
</table>

**Note:** Add a breakpoint prefix to any of the above classes to set padding dynamically at a certain breakpoint. For example, an element with `class="col pad-v tab-pad-all"` would have top and bottom padding on viewports up to 767px, and would add left and right padding to itself on viewports wider than that.

#### Margins ####

By default, there are no margins applied to `.col` and `.layer` elements in eb-grid. If you want to add top and/or bottom margin to an element, use one of the following:

<table width="100%">
  <thead>
    <tr>
      <th width="15%">Class name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.bump</td>
      <td>Sets 10px of margin on the top and bottom sides of the element. Does NOT set margins on the left and right sides.</td>
    </tr>
    <tr>
      <td>.bump-t</td>
      <td>Sets 10px of margin on the top side of the element. Leaves all other margins as-is (0 by default).</td>
    </tr>
    <tr>
      <td>.bump-b</td>
      <td>Sets 10px of margin on the bottom side of the element. Leaves all other margins as-is (0 by default).</td>
    </tr>
  </tbody>
</table>


## Support ##

If you have questions or suggestions about eb-grid, just create an issue. Thanks.
