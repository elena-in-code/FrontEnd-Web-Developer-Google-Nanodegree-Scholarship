## Index
* [Responsive](#responsive)
* [Media Query](#media-query)
* [Flexbox](#flexbox)
* [Responsive Patterns](#responsive_patterns)
* [Order](#order)

# Responsive:
```
img {
   max-width: 100%; 
}
```
Adding this, we make sure that the element will be always contain inside the container <br>
make elements always relative <br>

**Finger size**<br>
about 40px <br>
To fit any size of finger on a tap element 48x48<br>
```
a, input, button {
   min-width: 48px; 
   min-height: 48px; 
}
```
`min-height` will set a minimum but also will allow to resize if necessary, never bellow the minimum <br>
 
 # Media Query

 ## Ways to add media query

 **Link in the html:** <br>
 ```
 <link rel="stylesheet" media="screen and (min-width:500px)" href="over500.css">
 ```
 This css style sheet will only be applied when the screen it is over 500px, not smaller <br>
 Files smaller, more http requests<br>

**Embedded with media tag:**
 ```
 @media screen and (min-width:500px) {
     header{ background: red;}
 }
 ```
 Files bigger, less http requests<br>

**Import:**<br>
avoid to use this way because performance:
 ```
 @import url("style.css") only screen and (min-width:500px);
 ```

## Types of media query

**min-width**<br>
based on the browser window, not device<br>
 ```
 @media screen and (min-width:500px) {
     header{ background: red;}
 }
 ```
It will only be applied when the screen it is over 500px, not smaller <br>
more than the value specified <br>

**max-width**<br>
based on the browser window, not device<br>
 ```
 @media screen and (max-width:500px) {
     header{ background: red;}
 }
 ```
It will only be applied when the screen it is under 500px, not bigger <br>
less than the value specified <br>

Example: <br>
Under 400px wide, the body is red<br>
Between 401 and 599px wide, the body is green<br>
Greater than 600px wide, the body is blue<br>
```
@media screen and (max-width: 400px) {
    body{background-color:red;}
}
@media screen and (min-width: 401px) and (max-width: 599px) {
    body{background-color:green;}
}
@media screen and (min-width: 600px) {
    body{background-color:blue;}
}
 ```

# Flexbox

`display: flex;`
Makes elements to show in a row, it is the default flex-direction. And they will no wrap (keep them in the same line, no going to the next line), so they will be resize by the size of the browser window<br>
`flex-wrap: wrap;`
elements can go to the next line, so they dont need to be squeeze/resize. <br>
`order:1;`
added to the css element makes the elements follow the order indicated, and it can change if we decide to in different layouts.<br>


# Responsive Patterns:
 **Column drop:** <br>
  ```
 .main-container {
   display: flex;
   flex-warp: wrap;
 }
 ```
 All the divs inside of the main-container to 100% width.<br>
then play with media queries to make each divs different size in each screen size <br>

 **Mostly fluid:** <br>
   ```
 .main-container {
   display: flex;
   flex-warp: wrap;
 }
 ```
 All the divs inside of the main-container to 100% width.<br>
 the divs inside are different sizes <br>
 Reached a breaking point we can add `margin-left:auto;` and `margin-right:auto;` so will add margins and no longer expand the divs. <br>
 example: <br>
 [Fluid Layouts](https://codepen.io/Elena_in_code/pen/ERaQmG)
 
 # Order
 Set the order that inside the container the different divs will show up, by default all have set "0"
 so "-1" will ensure that will come first and 1 and above will come after.
