## View the website

To view the optimized website, open Chrome and go to:
https://neil-h-williams.github.io

## Optimizations made to files

### Changes made to index.html
* Compressed images and resized pizzeria.jpg.
* Added "async" attribute to scripts for Google analytics.
* Added "media print" attribute to css/print.css.
* Minified styles.css and inlined css in index.html.
* Commented out / removed google fonts.

### Changes made to main.js

#### Changes to "updatePositions" function:
* Changed "querySelectorAll" to "getElementsByClassName".
* Moved "document.body.scrollTop / 1250" and "items.length" out of the for loop and assigned them to variables. Reason: to get as many calculations and calls outside the for loop.
* (Tried changing style.left to transform: translateX(), but didn't see a difference in performance).

#### Changes to "changePizzaSizes" function:
* Moved the variables "oldWidth", "oldSize", and "windowWidth" from the "determineDx" function into the "changePizzaSizes" function. Reason: to move assignments and calculations outside of the main loop in "changePizzaSizes". "determineDx" function is now just "sizeSwitcher".
* Moved "document.querySelectorAll(".randomPizzaContainer")" outside the loop and assigned it to a variable.
* Changed the function "determineDx" to a simpler function "sizeSwitcher" to just calculate the size of the slider value.

#### Other changes:
* Added "will-change: transform" to .mover class in views/css/style.css (line 36). Reason: to place the animating pizzas on their own layer.
* Changed the number of pizzas from 200 to 40 for the for loop that generates the sliding pizzas (line 528). Reason: no need to animate 200 pizzas on the page.
* Moved the "i % 5" calculation from "updatePositions" to "elem.modulo = i % 5;" (line 535). Reason: to move some calculations out of the for loop in "updatePositions" function.
