# eb-grid
Responsive grid system that's laser-focused and more flexible than Bootstrap or Foundation. Tiny footprint, no class collisions.

**eb-grid is still a work in progress.**

### Why Bother? ###

Maybe you've been using Bootstrap or Foundation and realized that for one section your designer used an 8-column grid and for another a 5-column grid. And in one section, the elements all have padding, but in another, you need the content to come right up against the column edges. Or you want the rows to have some margin above and below them, but not the columns. Bootstrap and Foundation classes can't solve any of that for you. eb-grid can.

Also:

eb-grid is currently just **5.5 kb minified, and just 1.27 kb gzipped.** So there's almost zero performance impact.

It also **does not interfere** with, and can be used in the same project alongside, other responsive grids like Bootstrap and Foundation (as long as you're using them on separate elements). So you can use eb-grid as a patch to handle just a certain section, or slowly phase it into a legacy code base.

## Basics ##

eb-grid has a similar (but simpler) strategy as Bootstrap or Foundation, so if you know how to use those, you'll pick up eb-grid very quickly.

The main difference of eb-grid is that **instead of using a single, set 12- or 16-column grid structure, eb-grid uses fractions in its class names to allow you to set different column counts for each "layer" of content.** There are also some "helper"-style classes for optionally adding padding and margins to, really, any element in the framework: rows (layers) or columns (cols), on the fly.

>"Layers" are the same as Bootstrap's and Foundation's "rows". I wanted to be able to use eb-grid even if the project already uses Bootstrap or Foundation, so I've changed the class names to prevent any collisions.

### Basic Examples ###

      <div class="layer">
      
        <div class="col half">
          This will span half the width of the layer, always.
        </div>
        
        <div class="col half">
          This will span the other half of the width of the layer, always.
        </div>
        
      </div><!--/.layer-->
      
      
      
      <div class="layer">
        
        <div class="col ph-1-2 tab-1-5 lap-3-7 desk-5-8">
          This div will span:
          - 1/2 the width of the layer for viewports less than 768px,
          - 1/5 the width between 768 and 991px,
          - 3/7 the width between 992 and 1199px, and
          - 5/8 the width of viewports 1200px or greater.
        </div>
        
        <div class="col full pad">
          This will span the entire width of the layer, always,
          and will have 10px of padding on its left and right sides.
        </div>
        
        <div class="col full pad-all">
          This will span the entire width of the layer, always,
          and will have 10px of padding on all 4 of its sides.
        </div>
        
      </div><!--/.layer-->

## Classes ##

### Layers and columns ###

`.layer`

Like the `.row` class in Bootstrap, this wraps around all columns that should be positioned side-by-side, even if that's only at a certain viewport size.

`.col`

Also like Bootstrap, but without the appended viewport-size and column-width settings. These are blocks of content that will be positioned side-by-side in your layout. Note: `.col` can be used on the element even if it is the only element in the `.layer` and will span full-width at all times.

### Column widths, part 1: Breakpoints ###

There are 4 breakpoints in the eb-grid framework:

* ph (short for "phone")
* tab (short for "tablet")
* lap (short for "laptop")
* desk (short for "desktop")

There is also a print-specific class:

* print

These nicknames form the first part of any class name for a block of content, or `.col`.

eb-grid takes a mobile-first approach, so the `.ph` prefix is actually optional. For example:

    <div class="col ph-1-4"></div>

is the same as:

    <div class="col one-fourth"></div>

This alternate syntax might be easier to read and understand that the column should be 1/4 the width at all viewport sizes.

These `.ph` and un-prefixed classes will apply to elements at any viewport size, unless another class prefixed by `tab-`, `lap-`, or `desk-` is also added to the element (again, just like Bootstrap and Foundation).

<table>
  <thead>
    <tr>
      <th>Class prefix</th>
      <th>Viewport size it applies to</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>.ph-</td>
      <td>0 - 767px</td>
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
      <td>1200px +</td>
    </tr>
    <tr>
      <td>.print-</td>
      <td>Printed pages, regardless of size</td>
    </tr>
  </tbody>
</table>

### Column widths, part 2: Fractional widths ###

eb-grid allows you to easily set any fractional width up to eighths. I stopped there because I don't think any element should be narrower than that. Here is a table of all possible column widths, and the class names you can use for them:

<table>
  <thead>
    <tr>
      <th>Class suffix</th>
      <th>Optional stand-alone class name(s)</th>
      <th>Width of element in layer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>-full</td>
      <td>full</td>
      <td>100%</td>
    </tr>
    <tr>
      <td>-auto</td>
      <td>auto</td>
      <td>its auto/default size</td>
    </tr>
    <tr>
      <td>-1-2</td>
      <td>half, one-half</td>
      <td>50%</td>
    </tr>
    <tr>
      <td>-1-3</td>
      <td>third, one-third</td>
      <td>33.33333333%</td>
    </tr>
    <tr>
      <td>-2-3</td>
      <td>two-thirds</td>
      <td>66.66666667%</td>
    </tr>
    
    <tr>
      <td>-1-4</td>
      <td>fourth, one-fourth</td>
      <td>25%</td>
    </tr>
    <tr>
      <td>-3-4</td>
      <td>three-fourths</td>
      <td>75%</td>
    </tr>
    <tr>
      <td>-1-5</td>
      <td>fifth, one-fifth</td>
      <td>20%</td>
    </tr>
    <tr>
      <td>-2-5</td>
      <td>two-fifths</td>
      <td>40%</td>
    </tr>
    <tr>
      <td>-3-5</td>
      <td>three-fifths</td>
      <td>60%</td>
    </tr>
    <tr>
      <td>-4-5</td>
      <td>four-fifths</td>
      <td>80%</td>
    </tr>
    <tr>
      <td>-1-6</td>
      <td>sixth, one-sixth</td>
      <td>16.66666667%</td>
    </tr>
    <tr>
      <td>-5-6</td>
      <td>five-sixths</td>
      <td>83.33333333%</td>
    </tr>
    <tr>
      <td>-1-7</td>
      <td>seventh, one-seventh</td>
      <td>14.28571428%</td>
    </tr>
    <tr>
      <td>-2-7</td>
      <td>two-sevenths</td>
      <td>28.57142857%</td>
    </tr>
    <tr>
      <td>-3-7</td>
      <td>three-sevenths</td>
      <td>42.85714285%</td>
    </tr>
    <tr>
      <td>-4-7</td>
      <td>four-sevenths</td>
      <td>57.14285714%</td>
    </tr>
    <tr>
      <td>-5-7</td>
      <td>five-sevenths</td>
      <td>71.42857142%</td>
    </tr>
    <tr>
      <td>-6-7</td>
      <td>six-sevenths</td>
      <td>85.71428571%</td>
    </tr>
    <tr>
      <td>-1-8</td>
      <td>eighth, one-eighth</td>
      <td>12.5%</td>
    </tr>
    <tr>
      <td>-3-8</td>
      <td>three-eighths</td>
      <td>37.5%</td>
    </tr>
    <tr>
      <td>-5-8</td>
      <td>five-eighths</td>
      <td>62.5%</td>
    </tr>
    <tr>
      <td>-7-8</td>
      <td>seven-eighths</td>
      <td>87.5%</td>
    </tr>
  </tbody>
</table>

So **breakpoint prefix + fractional width suffix = class.** Use as many classes as you want to handle the element's width at each breakpoint. Example: `<div class="col ph-1-2 tab-2-3 lap-3-4 desk-4-5">`.

### Helper classes ###

The only other things eb-grid tries to handle are alignment and spacing on the layers and columns.

-----

**Alignment**

Set the alignment of text and other inline-displayed content using one of the following classes:

`.align-l`

Aligns content left.

`.align-r`

Aligns content right.

`.align-c`

Aligns content center.

`.align-col-l`

Floats block elements (like `.col`s) left.

`.align-col-r`

Floats block elements (like `.col`s) right.

`.align-col-c`

Floats block elements (like `.col`s) in the center of the layer.

`.first`

Use this class if the column should always be first (left-most) in a layer.

**Note:** You can also **add a breakpoint prefix to any of the above alignment classes,** to set text or column alignment specifically for a certain breakpoint. For example, an element with `class="col half tab-align-r tab-align-col-c desk-align-c desk-align-col-l"` would be centered in the layer with right-aligned text at 768px or wider, and would be floated left in the layer with centered text at 1200px or wider.

-----

**Padding**

eb-grid offers flexibility when it comes to padding on your layers and columns of content. By default there is no padding on the `.col` and `.layer` classes.

If you want to add padding to an element, use one of the following:

`.pad`

Sets 10px of padding on the left and right sides of the element. Does NOT set padding on the top and bottom (use `.pad-tb` or `.pad-all` for that).

`.pad-all`

Sets 10px of padding on all sides of the element.

`.pad-tb`

Sets 10px of padding on the top and bottom sides of the element. Does NOT set padding on the left and right sides (use `.pad` or `.pad-all` for that).

`.pad-l`

Sets 10px of padding on the left side of the element. Leaves all other sides 0.

`.pad-r`

Sets 10px of padding on the right side of the element. Leaves all other sides 0.

`.pad-t`

Sets 10px of padding on the top side of the element. Leaves all other sides 0.

`.pad-b`

Sets 10px of padding on the bottom side of the element. Leaves all other sides 0.

**Note:** You can also **add a breakpoint prefix to any of the above padding classes,** to set padding specifically for a certain breakpoint. For example. an element with `class="col tab-pad-r lap-pad desk-pad-all"` would have no padding in phone-sized viewports, 10px of right padding at 768px or wider, 10px of left and right padding at 992px or wider, and 10px of left, right, top, and bottom padding at 1200px or wider.

-----

**Margins**

Currently, eb-grid offers flexibility when it comes to margins on the top and bottom of your layers and columns of content. By default there is a net-zero left and right margin on the `.col` and `.layer` classes, and no top and bottom margin.

If you want to add top and/or bottom margin to an element, use one of the following:

`.bump`

Sets 10px of margin on the top and bottom sides of the element. Does NOT change the margins on the left and right sides.

`.bump-t`

Sets 10px of margin on the top side of the element. Leaves all other margins as-is.

`.bump-b`

Sets 10px of margin on the bottom side of the element. Leaves all other margins as-is.

## Support ##

If you have questions or suggestions about eb-grid, create an issue. I'd like this to be truly useful to developers who just need a flexible responsive grid system without any broader scope.
