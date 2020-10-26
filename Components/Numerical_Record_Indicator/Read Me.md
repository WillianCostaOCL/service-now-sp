# Numerical Record Indicators

Component that returns a record count from a table

![Indicators](https://github.com/WillianCostaOCL/service-now-sp/blob/main/Components/Numerical_Record_Indicator/img/indicators-img.png)


## STEP

1 - Create or use a Script include to add 'getRecordCount' function

```JAVASCRIPT

getRecordCount: function(table, filter){
		var ga = new GlideAggregate(table);
		ga.addAggregate('COUNT');
		ga.addEncodedQuery(filter);
		ga.query();

		if(ga.next())
			return  ga.getAggregate('COUNT');	
	},

```


2 - Add your Script Include in component (Server Script)


```JAVASCRIPT

	data.count = new YOUR_SCRIPT_INCLUDE().getRecordCount(data.table, data.filter);

```
