###### Graphics Programming - Exercise 7
# D3.js
In this exercise we will look at the library D3.js.

## Exercises
Save each step as a separate source file.

1. Create a blank HTML file with a CSS section and a JavaScript section, and add a canvas element to it.

    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <title>D3.js Demo</title>
        <style type="text/css"></style>
      </head>
      <body>
        <script type="text/javascript"></script>
      </body>
    </html>
    ```

1. Download and include d3.js.

    ```js
    <script type="text/javascript" src="d3.js"></script>
    ```
    
1. Create an array of ten random integers between 0 and 300 called mydata.

    ```js
    var mydata = [];
    for (var i = 0; i < 10; i++)
      mydata[i] = ...
    ```

1. Using D3, select the body tag and add an SVG tag to it.

    ```js
    var body = d3.select("body");
    var svg = body.append("svg");
    ```

1.  For each element in data, add a rect to the SVG. Set each rect to the same x, y, w and h for now.

    ```js
    var rects = svg.selectAll("rect")
                   .data(mydata)
                   .enter()
                   .append("rect")
                   .attr("x", 0)
                   .attr("y", 0)
                   .attr("width", 20)
                   .attr("height", 100);
    ```
    
1. Set the x position of each rect to a different value.

    ```js
    .attr("x", function(datum, index) {
      return index * 12;
    })
    ```

1. Then set the h value of each rect to the value of the datum.

    ```js
    .attr("h", function(datum, index) {
      return datum;
    })
    ```

1. Re-create the mydata array so that it is a list on ten new random values.

    ```js
    for (var i = 0;...)
      mydata[i] = ...
    ```

1. Change the rects on the SVG to reflect this new data.

  ```js
    var rects = svg.selectAll("rect")
                   .data(mydata)
                   .attr("height", function(datum, index) {return datum;});
  ```

1. Do the last two steps again, but this time with a transition.

    ```js
    for (var i = 0; i < 10; ...)
      mydata[i] = ...
      
    var rects = svg.selectAll("rect")
                   .transition()
                   .duration(750)
                   .delay(function(datum, index) {return index * 100;})
                   .attr("height", function(datum, index) {return datum;});
    ```

## Advanced exercises

1. Use a D3 scale to automatically make the largest bar the same height as the SVG (with a little padding), and scale the heights of the other bars in proportion.

1. Have the bars drawn from the bottom, rather than the top of the SVG.

1. Change the colour of each bar to be different to the others.

## Notes
- [The D3.js website](http://d3js.org/).

- [Tutorial on making a bar chart in d3.js.](http://bost.ocks.org/mike/bar/).

- [A great tutorial on D3.js](http://alignedleft.com/tutorials/d3/making-a-bar-chart).
