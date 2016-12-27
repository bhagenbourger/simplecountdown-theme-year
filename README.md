# Happy new year theme for simplecountdown
A theme for simple countdown

#Example with theme
Theme should be specified adding a third parameter to autoDisplay method. For use year theme, include simplecountdown-theme-year.js file in your page:
```javascript
<script type="text/javascript" src="simplecountdown.js"></script>
<script type="text/javascript" src="simplecountdown-theme-year.js"></script>
```

Add div container:
```HTML
<div id="myCountdown"></div>
```

Add js to load countdown:
```javascript
<script type="text/javascript">
  SimpleCountdown.autoDisplay('myCountdown', '2017-01-01 00:00:00', "year");
</script>
```

#Develop your own theme
To develop your own theme you have to call addTheme method with a json object in paramter like describe below:
```javascript
SimpleCountdown.addTheme(
  {
    myNewTheme: { // myNewTheme is the name of the theme, name to specify in method autoDisplay in third parameter
       content: {
         title: "My title" // Title displayed above the counter
       },
       style: {
         container: ".sc-container{}", // sc-container is the class of countdown container
         title: ".sc-title{}", // sc-title is the class of title div, add your css here to customize title
         brick: ".sc-brick{}", // sc-brick is the class of each div which contains number and legend
         number: ".sc-number{}", // sc-number is the class of each span in which numbers are displayed
         legend:".sc-legend{}" // sc-legend is the class of each span in which legend (day, hour, minute, second) is displayed
       }
     }
   }
);
```

#Develop your own theme with javascript callback
Since v1.4.0 it is possible to add a javascript callback called after the theme css application. This callback is optional, has no parameter and must be set in second paramter of addTheme function like describe below:
```javascript
SimpleCountdown.addTheme(
  {
    myNewTheme: { // myNewTheme is the name of the theme, name to specify in method autoDisplay in third parameter
       content: {
         title: "My title" // Title displayed above the counter
       },
       style: {
         container: ".sc-container{}", // sc-container is the class of countdown container
         title: ".sc-title{}", // sc-title is the class of title div, add your css here to customize title
         brick: ".sc-brick{}", // sc-brick is the class of each div which contains number and legend
         number: ".sc-number{}", // sc-number is the class of each span in which numbers are displayed
         legend:".sc-legend{}" // sc-legend is the class of each span in which legend (day, hour, minute, second) is displayed
       }
     }
   },
   function myAfterCallback(){console.log('my first callback');}
);
```
