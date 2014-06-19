d3.sketchy consists of three ways to make your dataviz look more sketchy:

d3.sketchy.circle creates an SVG circle element with an SVG path element over it that looks like a hand-drawn circle. The current circle outline is too static and needs to be improved, but by adjusting the strokeWidth property a bit among your circles, you can make them look different.

d3.sketchy.rect does the same things for rectangles and includes a .jostle property to make them more or less off-kilter.

d3.sketchy.randomColor takes a color and a range (between 0 and 1) and returns a color that has been perturbed along HSL by that range. Notice that pure hues need more perturbation to be readily visible.

The circles and rects work in a pretty straightforward manner similar to the SVG components already in D3:

      var sketchyRectangle = d3.sketchy.rect();
      sketchyRectangle
      .height(100)
      .width(50)
      .x(100)
      .y(100)
      .stroke("black")
      .strokeWidth(10)
      .jostle(5)
      
      d3.select("#someParent").call(sketchyRectangle);

Likewise for a circle:
      var sketchyCircle = d3.sketchy.circle();
      sketchyCircle
      .radius(15)
      .cx(150)
      .cy(150)
      .fill("red")
      .stroke("black")
      .strokeWidth(10);
      
      d3.select("#someContainer").call(sketchyCircle);

Sketchy colors are just:
d3.sketchy.randomColor("pink",.075);

Here's an [interactive example using circle-packing, brushing and bar charts](http://bl.ocks.org/emeeks/4e80576b894730d5cb6b). 