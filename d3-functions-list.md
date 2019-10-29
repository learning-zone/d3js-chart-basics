## D3.js COMMANDS 

#### D3.js Functions 

|Sl.No.| Method                       | Example                           |
|------|------------------------------|-----------------------------------|
|  01. |d3.scale()                    |  d3.scale.linear(), d3.scale.log(), d3.scale.pow()|
|  02. |d3.svg.axis()                 |                                     |
|  03. |d3.ticks(4);                  |  Create label range for x and y axis|
|  04. |svg.transition()              |                                     |
|  05. |svg.duration(500)             |                                     |
|  06. |svg.ease('linear')            |      elastic, circle, bounce        |
|  07. |svg.append('title').text(function(d){return d;});| tooltip          |
|  08. |d3.svg.line()	 			| create a new line generator|
|  09. |d3.svg.line.radial()	 	| create a new radial line generator|
|  10. |d3.svg.area() 				| create a new area generator|
|  11. |d3.svg.area.radial() 		| create a new radial area generator|
|  12. |d3.svg.arc() 				| create a new arc generator|
|  13. |d3.svg.symbol() 			| create a new symbol generator|
|  14. |d3.svg.chord() 				| create a new chord generator|
|  15. |d3.svg.diagonal() 			| create a new diagonal generator|
|  16. |d3.svg.diagonal.radial() 	| create a new radial diagonal generator|


#### D3.js Selections 

|Sl.No.| Method            | Description                           |Example                          |
|------|-------------------|-------------------------------------- |---------------------------------|
| 01.  |d3.select() 	   |Returns the element found 					|d3.select("svg")|
| 02.  |d3.selectAll() 	   |Returns all found elements 					|d3.selectAll("circle")|
| 03.  |selection.append() |Creates a new element inside the selection 	|d3.select("svg").append("circle")|
| 04.  |selection.remove() |Removes the selection from the DOM 			|d3.select("rect").remove()|
| 05.  |selection.text()   |Sets the text content of the selection 		|d3.select("#tooltip").text("")|
| 06.  |selection.attr()   |Set an HTML attribute value on the selection |d3.selectAll("circle").attr("r",	10)|
| 07.  |selection.style()  |Set an inline CSS style on the selection 	|d3.selectAll("circle").style("fill",        	"teal")|
| 08.  |selection.classed()| Adds or removes a class from the selection    |d3.select("circle").classed  ("highlight",	true)|


#### D3.js Transitions

|Sl.No.| Method         | Value                   |Description                          |
|------|----------------|-------------------------------|---------------------------------|
| 01.  |selection.transition() 	|						|Starts a transition on this selection. |
| 02.  |.duration 				|Number of milliseconds | Specifies the time during which the transition will take place. Default is 250ms.|
| 03.  |.delay 			|Number of milliseconds |Specicies the time that the system will wait before firing the transition. default is 0 (instant). |
| 04. |.attr 			|String (attr. name), value |The target attributes for the selection.|
| 05. |.style 			|String (style name), value |The target styles for the selection. |
| 06. |.each 			|“end”, function 			|This launches function at the end of the current transition.|

Example
```javascript
// moves that rectangle to 100 pixels from the left of its container
d3.select("rect").transition().delay(100).duration(1000).attr("x",100) 

// turns it to red
d3.select("rect").transition().style("fill","red"); 

// makes it transparent, and when it's completely transparent, delete it.
d3.select("rect").transition().style("opacity",0).each("end",function() {d3.select(this).remove();}) 
```

#### D3.js Scales

|Sl.No.| Method         | Description                           |Example                          |
|------|----------------|---------------------------------------|---------------------------------|
| 01. |d3.scale.linear()|Creates a new linear scale function 	|var	xScale	=	d3.scale.linear()|
| 02. |scale.domain() 	|Sets the scale’s input domain 	 	 	|.domain([	0,	2000	])|
| 03. |scale.range() 	|Sets the scale’s output range 	 	 	|.range([	0,	width	]);|
| 04. |d3.min() 		|Returns the smallest value in an array |d3.min([	10,	20,	70,	35	])		//	Returns	10|
| 05. |d3.max() 		|Returns the largest value in an array 	|d3.max([	10,	20,	70,	35	])		//	Returns	70|


#### D3.js Axes

|Sl.No.| Method         | Description                                  |Example                          |
|------|----------------|----------------------------------------------|---------------------------------|
| 01. |d3.svg.axis() 	|Creates a new axis generator function 		   |var	xAxis =	d3.svg.axis()|
| 02. |axis.scale() 	|Specifies the scale to be used with this axis |	 	 	.scale(xScale)|
| 03. |axis.orient() 	|Specifies the orientation for this axis 	   | 			.orient("bottom")|
| 04. |axis.ticks() 	|Suggests a number of ticks for this axis 	   | 			.ticks(5);|
| 05. |selection.call() |Calls a method; used to generate an axis 	   |	svg.append("g").call(xAxis);|


#### D3.js Quantitative scales

|Sl.No.| Method         | Description                                                                   |
|------|----------------|-------------------------------------------------------------------------------|
| 01.  |d3.scale 		|The beginning of every scale. 
| 02.  |domain 			|The interval of values to transform. It is an array of 2 or more ordered values. 
| 03.  |range 			|The interval of values in which to be transformed. 
| 04.  |Linear 			|The linear scale transforms one value in the domain interval into a value in the range interval     (without transformation)| 
| 05.  |pow 				|The pow scale transforms one value in the domain interval, raised to a certain power, into one value in the range interval.|
| 06.  |Exponent 		|For the pow scale, the exponent method allows to specify an exponent (1 by default, equivalent to     linear).
| 07.  |sqrt 			|Transforms the square root of one value in the domain interval into one value in the range    interval. Equivalent to d3.scale.pow().exponent(.5)|
| 08.  |log 				|Transforms the log of one value in the domain interval into one value in the range interval.
| 09.  |identity 		|The identity scale doesn’t transform a value, but is useful when you need a scale object, specify     a range etc.|
| 10.  |quantize 		|If the value is between the kth and the k+1th value of the domain, returns the kth value of the    range. |
| 11.  |threshold 		|If the value is between the kth and the k+1th value of the domain, returns the k+1th value of the     range.|
| 12.  |quantile 		|This is the one scale that doesn’t require the domain and range to have the same cardinality. It divides the domain into i intervals, where i is the cardinality of the range array. Then, if a value if in the kth interval, it returns the kth value of the range. |									
| 13.|invert 			|The opposite of the scale. If s is a scale and s(x)=y, then s.invert()(y) = x. 
| 14.|nice 			|Extends the domain of the scale so that its bound are round values.
| 15.|rangeRound 		|(use instead of range). Makes it so that the output of the range are rounded to integer values.
| 16.|interpolate 		|Takes a function (“factory”). Allows to override how d3 maps values from the domain to the range.
| 17.|clamp 			|If set to [true], if a value is outside the domain, it will be transformed into either the lower or the upper bound of the range.|


Example
```javascript
var s1=d3.scale.linear().domain([0,10]).range([50,100]); s1(5) // 75
var s2=d3.scale.pow().domain([0,10]).rangeRound([50,100]).exponent(2); s2(9) // 91
var s3=d3.scale.threshold().domain([0,2,5,10]).range([50,100,150,200]);s3(3) // 150
var s4=d3.scale.quantile().domain([0,10]).range([0,1,2,3]); s4(4) // 1
var s5=d3.scale.linear().domain([0,10]).range([50,100]).clamp([true]); s5(15) // 100
```

#### D3.js Force Layout 

|Sl.No.| Method         | Description                                                                   |
|------|----------------|-------------------------------------------------------------------------------|
| 01. |nodes | 	Nodes is an array of objects that will be used as the nodes.                            |
| 02. |gravity | It is a force that can push nodes towards the center of the layout.	                |
| 03. |friction  | At each step of the tick, node movement is scaled by this friction. The recommended range of friction is 0 to 1, with 0 being no movement and 1 being no friction.|
| 04. |charge | The charge in a force layout refers to how nodes in the environment push away from one another or attract one another. Kind of like magnets, nodes have a charge that can be positive (attraction force) or negative (repelling force).|	
| 05. |alpha | The alpha is the layout is described as the simulation’s cooling factor.|


