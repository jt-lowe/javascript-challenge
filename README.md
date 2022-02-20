# javascript-challenge
## Monash Data Analytics Course Week 14

### UFO 1 - Automatic Table and Date Search
#### Filling the table
First we connect the data from our data.js file to the Javascript file and store it in a variable. 

As the table will be stored within the "tbody" element we can also create a variable to store that location in d3 using the select function.

Using arrow notation and the .forEach function we append "tr" for each row in the data set, and "td" for each cell that is needed (i.e. amount of columns in the output table). The value from each key:value pair is also appended into the "cells" that we create.

#### Date Search
We create variables to hold both the button and form in the html, through the d3.select() function, this is followed with event handlers to capture when the button is clicked or when the form is submitted with the "enter" key.

The ufoFilter function we created begins with a .preventDefault() function so that the webpage does refresh when the above events occur, allowing us to preserve the data.

The input date is saved by finding the corresponding element attached to the form (in this case the #datetime id was used) and the value is extracted using the .property("value") attribute.

The filter is then created and mapped to a variable using arrow notation, filtering to check the original datetime data matches the input value.

The filtered data is then input into the table using the same actions we used in the above section, using forEach to append rows,columns and data into the table.

Further we create an if/else condition to check whether the input value is not empty, and if it is we reinput the original dataset, this is to capture the event that the filter is placed and then removed, as we don't want the page to ever be empty of data.