## D3.js Data Visualization Interview Questions and Answers

*Click <img src="https://github.com/learning-zone/d3js-interview-questions/blob/master/assets/star.png" width="18" height="18" align="absmiddle" title="Star" /> if you like the project. Pull Request are highly appreciated.*


#### Q. What is SVG?
SVG or Scalable Vector Graphics (SVG) is an XML, the markup language for determining two-dimensional vector graphics. SVG is crucial for graphics what XHTML to text.
```html
<!-- Rectangle -->
<div>Rectangle</div>
<svg width="200" height="200">
    <rect x="5" y="5" width="190" height="190" fill="#1e90ff"></rect>
</svg>


<!-- Line -->
<div>Line</div>
<svg height="200" width="200">
    <line x1="0" y1="0" x2="200" y2="200" style="stroke:rgb(255,0,0);stroke-width:2" />
</svg>


<!-- Circle -->
<div>Circle</div>
<svg height="200" width="200">
    <circle cx="100" cy="100" r="45" stroke="#333" stroke-width="2" fill="orange" />
</svg>


<!-- Text -->
<div>Text</div>
<svg height="200" width="250">
    <text x="10" y="120" font-family="sans-serif" font-size="25" style="fill: #333;">SVG Text Example</text>
</svg>


<!-- Polyline -->
<div>Polyline</div>
<svg height="200" width="200">
    <polyline points="10 35, 30 10, 50 35" stroke="green" fill="transparent" stroke-width="2" />
</svg>
```

[Live Example](https://learning-zone.github.io/d3js-interview-questions/a.svg.html) 

#### Q. What is the difference between canvas and SVG in d3.js?
SVG is abbreviated as **Scalable Vector Graphics**. It is a vector-based graphics and used the XML based format for graphics providing the support for interaction. SVG images are way better than bitmap images.  In SVG images, the vector image is composed of a fixed set of shapes and while scaling these images it preserves the shape of the image. 

Canvas is an HTML element, which is used to draw graphics on the web page. It is referred to as a bitmap with an immediate mode graphics application programming interface. For drawing on it. The element canvas is used as a container for graphics. In Canvas, we need the script to draw the graphics.
```html
<canvas id="myCanvas" width="800" height="800"></canvas>
```
```javascript
var canvas = document.getElementById('myCanvas');
var context = canvas.getContext('2d');
context.fillStyle = '#c00';
context.fillRect(10, 10, 100, 100);
```

**Canvas vs SVG in D3**  
With SVG, data binding is easy - we can assign a datum to an individual svg element and then use that datum to set its attributes/update it/etc. This is built upon the statefulness of svg - we can re-select a circle and modify it or access its properties.

With Canvas, canvas is stateless, so we can't bind data to shapes within the canvas as the canvas only comprises of pixels. As such we can't select and update elements within the canvas because the canvas doesn't have any elements to select.

In D3js the `enter`/`update`/`exit` cycle (or basic append statements) are needed for svg in idiomatic D3: we need to enter elements to see them and we style them often based on their datum. With canvas, we don't need to enter anything, same with `exiting`/`updating`. There are no elements to append in order to see, so we can draw visualizations without the `enter`/`update`/`exit` or the append/insert approaches used in d3 svg visualizations.

#### Q. Explain selections in d3.js?
D3 Selections allow data-driven transformation of the document object model (DOM): set attributes, styles, properties, HTML or text content, etc. Using the data join’s enter and exit selections, you can also add or remove elements to correspond to data.


|Method	                    |Description |
|---------------------------|---------------------------------------------------------------------------------------|
|d3.select(css-selector)	|Returns the first matching element in the HTML document based on specified css-selector|
|d3.selectAll(css-selector)	|Returns all the matching elements in the HTML document based on specified css-selector|

```html
<div class="container">
    <h2>Select DOM Elements using D3</h2>
    <section id="chart">
        <div class="item">Barot Bellingham</div>
        <div class="item">Hassum Harrod</div>
        <div class="item">Jennifer Jerome</div>
        <div class="item">Richard Tweet</div>
        <div class="item">Lorenzo Garcia</div>
        <div class="item">Xhou Ta</div>
    </section>
</div>
```
```javascript
    d3.selectAll('.item:nth-child(2n)')
            .style("color", "green");
```

[Live Example](https://learning-zone.github.io/d3js-interview-questions/b.selection.html)

#### Q. Explain about d3.js Scales?
D3.js scales come with

* **Quantitative Scales**: The quantitative scales have a continuous domain like dates, times, real numbers etc.
* **Ordinal Scales**: While the ordinal scales are for separate domains like categories, colors, names,
* **Linear Scales**: It converts one value in the domain interval into a value in the range interval
* **Identity Scales**: It is good for pixel values
* **Power and Logarithmic Scales**: It is used for exponentially increasing values like log,pow,sqrt

[Live Example](https://learning-zone.github.io/d3js-interview-questions/i.scales.html)

#### Q. What are the slider available in d3.js?
The slider available in d3.js are

* Default slider
* Slider with start value
* Slider with slide event
* Slider with slide event
* Slider with custom axis
* Slider with min, max, and step values
* Vertical Slider

#### Q. What is Domain in d3.js?
In d3.js, domain is the start and end of your dataset. It can be any kind of value that can be compared in JavaScript. Domains have to change if your dataset changes.

#### Q. What is the role of “Path Data Generator” in d3.js?
In respect to convert our data to the SVG path command, we have to tell the line Path Data Generator, about how to access the y and x co-ordinates from the data.

#### Q. What does path generators include in it?
Path generator includes

* `svg.line`- Make a new line generator
* `svg.line.radial`- Make a new radial line generator
* `svg.area` – Make a new area generator
* `svg.chord` – Make a new chord generator and so on

#### Q. What d3.js enter method does?
D3.js enter method returns the virtual enter selection from the data operator.  This method is only applicable to Data Operator as such data operator is the only one that returns three virtual selections.

#### Q. What is the difference between jQuery and d3.js?

#### Q. What is the role of D3.js Axis component?
D3.js Axis component enables easy addition of a horizontal axis and the vertical axis to any graph. It shows reference lines for D3.js Scales automatically. It also allows you to draw a horizontal axis line, axis ticks and correct spacing to make axis appear appropriate.

#### Q. Mention the command used to create simple axis in d3.js?
The command to create simple axis in d3.js is var xAxis = d3.svg.axis().

#### Q. What is SVG group element?
SVG group element is used to group SVG element together; each SVG group element is a container which consists of child SVG elements.  It is defined by <g> and </g>.

#### Q. How you can several classes at once?
To set several classes at once you can use the object literal as

selection.classed({ ‘foo’:true, ‘bar’: false})

#### Q. What is a transition in d3.js?
Transition in d3.js gradually interpolate attributes and styles over time, transition is used for animation purpose.  It is based on only two key frames, start, and end.  The starting key frame defines the current state of the DOM, while the ending key frame is a set of styles, attributes and other properties you specified.

#### Q. What is the command to interpolate two objects in d3.js?
To interpolate two objects in d3.js command d3.interpolateObject(a,b) is used. Object interpolation is useful particularly for data space interpolation, where data is interpolated rather than attribute values.

#### Q. What is the command “d3.ascending (a, b)” is used?
This command is comparator function that is used for a natural order, and can be used along with the built-in-array sort method to arrange elements in ascending order.

#### Q. How XML file is called in d3.js?
By using the command d3.xml(url[mimeType][,callback]) XML file can be called. This command will create a request for the XML file at the specified url. If a call back is declared, the request will be immediately processed with the GET method and the call back will be invoked when the file is loaded, or request fails.

#### Q. What happens if no call back is specified for XML file in d3.js?
If no call back is specified, the returned request can be issued using xhr.get and handled using xhr.on.

#### Q. Mention the command to join the specified array of data in d3.js?
To join the specified array of data in d3.js you can use the command `selection.data([values[,key]])`.  The values here specifies the data for each group in the selection while a key function determines how data is connected to elements.

#### Q. What does the command d3.csv.parseRows(string[,accessor]) ?
This command parses the specified string, which is the content of a CSV file, returning an array of arrays representing the parsed rows.

#### Q. What is the use of “Enter” and “Exit” selection in d3.js?
By using “Enter” and “Exit” selection in d3.js, you can create new nodes for incoming data and eliminate outgoing nodes that are no longer required.

#### Q. How d3.js identify on which elements to operate?
#### Q. What is the best way to create the stacked chart in d3 js?
#### Q. How to import XML data using d3.js?
#### Q. What is different between d3.scale.linear() and d3.scaleLinear()?
#### Q. How to set initial zoom level in d3.js?
#### Q. How to resize an SVG when the window is resized in d3.js?
#### Q. How to get mouse position in d3.js?
#### Q. How to format the date in d3.js?
#### Q. Explain axes in d3.js? How to create d3.js axes without numbering?
#### Q. How to calculate the area of the polygon in d3.js?
#### Q. How data binding work in d3.js?
#### Q. How to handle events in d3.js?
