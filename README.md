<html>
	<meta charset="utf-8">
<head>
    <script src="https://d3js.org/d3.v4.min.js"></script>
</head>

<body>
	<title>Musk Twitter Deal </title>
	<section>
		<h1 style="font-size: 300%;text-align: center; margin-bottom: -20px;"> HEADLINE GOES HERE </h1>
		<h2 style="text-align: center; font-size: 200%;"> Sub Heading Goes Here </h2>
	</section>
</body>	

<div id = "twitter_musk"></div>
	<script>
		var margin = {top:20, right: 30, bottom: 40, left: 90},
			width = 500 - margin.left - margin.right,
			height = 400 - margin.top - margin.bottom;

		var svg = d3.select("#twitter_musk")
					  .append("svg")
					    .attr("width", width + margin.left + margin.right)
					    .attr("height", height + margin.top + margin.bottom)
					  .append("g")
					    .attr("transform",
					          "translate(" + margin.left + "," + margin.top + ")");

	d3.csv("https://raw.githubusercontent.com/pulkitm91/DV/main/lbo_data.csv", function(data) {

		var x = d3.scaleLinear()
		    .domain([0, 45])
		    .range([ 0, width]);
		  
      	var y = d3.scaleBand()
		    .range([ 0, height ])
		    .domain(data.map(function(d) { return d.Deal; }))
		    .padding(.15);	

		svg.selectAll("mybar")
		    .data(data)
		    .enter()
		    .append("rect")
		    .attr("y", function(d) { return y(d.Deal); })
		    .attr("height", y.bandwidth() )
		    .attr("width", function(d) { return x(0); })
		    .on("mouseover", function() { d3.select(this)
				.attr("fill", "#509d8b");})
		    .on("mouseout", function() { d3.select(this)
		    	.attr("fill", "#98cabf");})
		    
		    .transition()
			.duration(2000)
			.attr("width", function(d) { return x(d.Value); })
			.attr("fill", "#98cabf")


		svg.selectAll("text")
			.data(data)
			.enter()
			.append("text")
			.text(function(d) {return d.Amount; })
			.attr("y", function(d,i) {return i*(height/data.length)+ 25;})
			.attr("x", function(d) {return x(d.Value) - 50;})
			.attr("font-family", "arial")
			.attr("font-size", "20px")
			.attr("fill", "#000101")

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -40 )
			.attr("y", 0)
		    .attr("width", 30)
		    .attr("height", 40)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/3fe6c258784fdbe5bc10a901ec4c2d5d033121bc/twitter.PNG")	
		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -60)
			.attr("y", 20)
		    .attr("width", 50)
		    .attr("height", 70)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/TXU.PNG")	

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -80)
			.attr("y", 40)
		    .attr("width", 80)
		    .attr("height", 100)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/first%20data.PNG")	

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -82)
			.attr("y", 70)
		    .attr("width", 80)
		    .attr("height", 100)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/rjr.PNG")	

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -45)
			.attr("y", 105)
		    .attr("width", 40)
		    .attr("height", 100)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/dell.PNG")	

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -65)
			.attr("y", 130)
		    .attr("width", 60)
		    .attr("height", 120)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/heinz.PNG")	

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -90)
			.attr("y", 150)
		    .attr("width", 90)
		    .attr("height", 140)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/EquityOffice.PNG")	

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -70)
			.attr("y", 180)
		    .attr("width", 60)
		    .attr("height", 140)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/HCA.PNG")	

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -82)
			.attr("y", 215)
		    .attr("width", 80)
		    .attr("height", 145)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/hilton.PNG")	

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", -70)
			.attr("y", 250)
		    .attr("width", 60)
		    .attr("height", 145)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/bots.PNG")

		svg.selectAll(".images")
			.data(data)
			.enter()
			.append("svg:image")
			.attr("x", 160)
			.attr("y", 160)
		    .attr("width", 300)
		    .attr("height", 180)
		    .attr("xlink:href", "https://raw.githubusercontent.com/pulkitm91/logo_images/main/deal.PNG")

	})

	</script>

</html>	
