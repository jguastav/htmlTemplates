# htmlTemplates
Simple Draft Solution To Show a Json on a Static HTML using Frontend Libraries

In this project are shown 2 solutions:
- React Solution
- Vue Solution

It is not intended to be a production project , but it allows with few changes to have available a static HTML reading a javascript with json data

This allows to easily change the JSON and test the HTML with diverse set of data. 

It could be interesting also to those developers, designers that have HTML knowledge but don't know about frameworks like React or Vue.

This is not the way to use React or Vue but it is a useful way of using it without any introduction. 


## JSON File
The HTML shows and uses the data that is in the file: https://github.com/jguastav/htmlTemplates/blob/master/jsonData01.js
You can easily change the data file importing any other file. 



## React

See : https://github.com/jguastav/htmlTemplates/blob/master/reactTemplateExample.html

### Input Values

Simply use the json data between {}
e.g. : value={myJson.channel}  
inside an input tag

### Static Data
use the json data between {}
e.g. {myJson.channel} inside the first <a> tag

### Style

Create a const with a neme:

e.g. 
		const divStyle = {
  			margin: '40px',
  			border: '5px solid pink',
  			color: myJson.colorValue
		};
    
    As you can see... the color attribute is getting its value from the json data
They you can apply the style as
    
    style={divStyle}
    
    
    

### Class

Replace the class HTML attribute to className
If the values for the classes are boolean in the json you can define if the class should be present as 

className={myJson.isClassFoo?"errorClass":"" }

In that case... if the json isClassFoo is true... it would set "errorClass" ... if not... it would not be there. 


### href

For href simply make reference to the json value closing the json variable between {}

e.g. : <a href={myJson.sites[2].url}>


## Vue

See: https://github.com/jguastav/htmlTemplates/blob/master/vueTemplateExample.html

In this case you don't need to refer to the variable myJson as preceding each json value. The myJson variable is a parameter when building the Vue environment.

You can see it in 

  <script type="text/javascript">
    new Vue({
      el: '#app',
      data: myJson});
  </script>
  
  
### Input Values

In the input tag use
e.g.  v-model="name" 
 
 instead of the HTML "value" attribute
 
 The "name" string refers to the name value inside the  JSON

### Static Data
use the json data between {{}}
e.g. {{channel}} inside the first <a> tag

### Style

use the JSON variable inside the v-bind:style tag (instead of the style HTML attribute)

v-bind:style="{margin:'40px' ,border:'5px solid pink',color:colorValue}"


### Class

Replace the class HTML attribute to v-bind:class

e.g. 
v-bind:class="{errorClass:isClassFoo}" 

being isClassFoo a boolan value from the JSON

If the value of the JSON property is true, then errorClass will be present

### href

Simply use the JSON property between "" on a v-bind:href attribute.

e.g. <a v-bind:href="youtubeUrl">


