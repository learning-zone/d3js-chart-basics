## D3.js COMMANDS 

#### D3.js Functions List

|Sl.No.| Functions                    | Example                           |
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


#### D3.js Selections List

|Sl.No.| Selections        | Description                           |Example                          |
|------|-------------------|-------------------------------------- |---------------------------------|
| 01.  |d3.select() 	   |Returns the element found 					|d3.select("svg")|
| 02.  |d3.selectAll() 	   |Returns all found elements 					|d3.selectAll("circle")|
| 03.  |selection.append() |Creates a new element inside the selection 	|d3.select("svg").append("circle")|
| 04.  |selection.remove() |Removes the selection from the DOM 			|d3.select("rect").remove()|
| 05.  |selection.text()   |Sets the text content of the selection 		|d3.select("#tooltip").text("")|
| 06.  |selection.attr()   |Set an HTML attribute value on the selection |d3.selectAll("circle").attr("r",	10)|
| 07.  |selection.style()  |Set an inline CSS style on the selection 	|d3.selectAll("circle").style("fill",        	"teal")|
| 08.  |selection.classed()| Adds or removes a class from the selection    |d3.select("circle").classed  ("highlight",	true)|
