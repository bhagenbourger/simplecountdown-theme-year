# Happy new year theme for simplecountdown
A theme for simple countdown

## Example with theme
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
  SimpleCountdown.autoDisplay('myCountdown', '2017-01-01 00:00:00', true, "year");
</script>
```

## Develop your own theme
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
         custom: ".sc-custom{}" // optional style for the custom div, sc-custom is the class of custom div which display the custom content (myNewTheme.content.custom)
       }
     }
   }
  function myCallback(){console.log('my callback')}, // optional callback called after the theme css application, this callback has no parameter and must be set in second parameter of addTheme function
  function myCallbackZero(){console.log('my callback zero')} // optional callback called when time is over, this callback has no parameter and must be set in third parameter of addTheme function
);
```

## Release management (must be automated)
- checkout master
- run `npm install`
- create new PR for branch $npm_package_version
- merge the PR
- checkout master
- run `npm publish`