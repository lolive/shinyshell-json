# Package "Shinyshell-json":

This package contains the following functions:


## jsoninnerpaths  :

Retrieves JSON paths from standard input (usually the result of command jsonpaths), strips the leading path item, and sort/uniq the rest.

For example, for paths:
a.b.m
a.c.m
b.b.y
b.c.m
b.d.z

this command returns:
b.m
b.y
c.m
d.z


## jsonpaths _JSON_FILENAME :

Lists the paths of the input JSON.
The input can either be the json file given as argument $JSON_FILENAME.
If no argument is given, standard input is used.

For this input JSON data:
{ "a": ["x","y"],
  "b": {
       "c": 1
       }
}

the returned paths are:
a.0
a.1
b.c

Note: OpenFoodFacts require to strip the first element of each path and sort/uniq the paths.
We factorized this step in function jsoninnerpaths.

