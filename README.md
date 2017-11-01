# Express-notes-to-myself
Express notes to myself.

## What is Express ?
  
  Fast, unopinionated( means flexible), minimalist web framework (and its a framework not a library [Inversion-of-control](https://www.programcreek.com/2011/09/what-is-the-difference-between-a-java-library-and-a-framework/) )
  for Node.js.
  
  
 *Ok enough of theory, lets see some code.*
 
 ```
var express = require('express');   // Using package express in our project 
var app = express();                // Get an instance of express.

app.use(express.static('public'));  // Way to tell express that all your static pages (.css or img) can be found in public folder
app.set('view engine', 'ejs');      // tell express to set your view engine to be ejs so you don't have to suffix filenames with .ejs when calling res.render

app.get('/', function (req, res) {  // On match of route '/' execute everything inside the function.
    res.render('some');
});


app.get('/:test', function (req, res) {   // match anything after /
    var test = req.params.test;
    res.render('some1' , {test: test});
});

app.get('*', function (req, res) {        // Global match.
  // Execute some code.
});

app.listen('3000', '', function () {      // Listen to port number 3000
   console.log('Server is listening!!');
}); 
```

