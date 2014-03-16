# Props2Js

Props2Js is a command line utility that converts Java properties files into one
of four different formats:

1. JSON
1. JSONP
1. JavaScript
1. Pods.js module

The goal is to allow you to easily store configuration data that is needed for
JavaScript in a simple format and then transform it into a format you need in
your application.

## Formats

### JSON Format

To convert a properties file into JSON, use the following

    java -jar props2js-x.y.z.jar source.properties -t json -o output.json

This reads in the properties file `source.properties` and outputs the JSON
equivalent into `output.json`.

### JSONP Format

To convert a properties file into JSON, use the following

    java -jar props2js-x.y.z.jar source.properties -t jsonp --name myfunc -o output.jsonp

This reads in the properties file `source.properties` and outputs the JSONP
equivalent into `output.jsonp`. This is the same as outputting as JSON except
`myfunc()` is wrapped around the data.

### JavaScript Format

To convert a properties file into JavaScript, use the following

    java -jar props2js-x.y.z.jar source.properties -t js --name myvar -o output.js

This reads in the properties file `source.properties` and outputs the JavaScript
equivalent into `output.js`. This is the same as outputting as JSON except
`var myvar=` precedes the JSON and a semicolon follows it.

### Pods.js module Format

To convert a properties file into a Pods.js module, use the following

	java -jar props2js-x.y.z.jar source.properties -t pods --name moduleName -o output.js
	
This reads in the properties file `source.properties` and outputs the Pods.js module
equivalent into `output.js`. This is the same as outputting as JSON except
`Pod.declare('moduleName', ` precedes the JSON and a closing bracket and a semicolon follows it.