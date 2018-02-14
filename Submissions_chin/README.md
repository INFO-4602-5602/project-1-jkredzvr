Justin Chin (no collabs)

Used Code Snippets from....
1. Line graph generation
https://bl.ocks.org/mbostock/3883245

The d3.line method returns the coordinates of the x,y path for an array of coordinates passed into the function.  When appending a path element, the sorted coordinates are passed to the line method and set as the path's d attribute.  

2. Sorting columns
http://www.jeromecukier.net/blog/2012/05/28/manipulating-data-like-a-boss-with-d3/
- sort method iterates through each pair of values and returns the ordered pair.  This continues iterating through the entire array until the whole array is sorted.

3. Mouse over events
http://bl.ocks.org/WilliamQLiu/76ae20060e19bf42d774
https://stackoverflow.com/questions/20414980/d3-select-by-attribute-value

An on mouse over and mouse out event is appended to each circle element (points on graph).  Mouse over and out each call handleMouseOver/Out methods.  Mouse over selects the element (circle DOM) and modifies the fill color and increases the radius size.  It also appends a text DOM to the svg with and id (taken from the dom's x,y coordinate), and positions it offset from the circle DOM's original position.  The text value is the data object's x and y value.  

On MouseOut, the method returns the circle DOM's color and size property back to normal, and selects the textDOM that was created using the id name created from handleMouseOver and calls remove() to delete it.

handleMouseClick simply gets the DOM's data's x and y values, finds the DOM with id scatterlabel, and changes the text to reflect the x and y value.

4. Graph title
http://www.d3noob.org/2013/01/adding-title-to-your-d3js-graph.html
Append a text element at the top (attr y ~ 0) of the graph and centered (attribute x to be half the width)

5. Multiple Plotted Graph
http://www.d3noob.org/2013/07/arranging-more-than-one-d3js-graph-on.html
Create new width, height variables to a 1/4 of the original specified in the previous graphs.  Create 4 new svgs using the new width and hegiht variables.

6. Bar chart plots
https://bl.ocks.org/mbostock/3885304
Taking the raw data, I created a frequency chart by looping through each row and creating a new object that stores the counts of X and Y values respectively.  The object was then created into an array of objects using d3.entries which then can be processed by d3 commands for plotting. 

The x axis values or domain is simply the keys of the objects in the x frequency array and y frequency array.  This is set mapping all keys directly using .map(function(d) { return d.key; }.

The bars are rects with the width's set by bandwidth(), which equally distributes the width size according the set svg width and number of bars in the data.  The height of the bar is the height of the svg subtracted by the frequency mapped along the y axis.



Bell: Tooltips (DONE)
Create a tooltip that shows the x- and y-value of each point when you hover over a point in the Part 3 scatterplot.

Bell: Xs and Ys (DONE)
For your bar chart code, create a pair of bar charts for the active dataset: one coding the x-value and one coding the y-value of the current dataset. You can only receive credit for one of this and the “Coordinated Views” whistle.
