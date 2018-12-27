# Package "Shinyshell-json":

This package contains the following functions:


## allpaths _JSON_FILENAME :

<pre>
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
The command to run for that is:
cat off.json | allpaths |innerpaths|uniqpaths
</pre>


## innerpaths  :

<pre>
Retrieves JSON paths from standard input (usually the result of command jsonpaths), strips the leading path item.

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
c.m
d.z

Note: this command does not sort|uniq the list. Pipe it into command 'uniqpaths' if you need that feature.
</pre>


## uniqpaths  :

<pre>
Retrieves JSON paths from standard input (usually the result of command jsonpaths) and sort|uniq them.

For example, for paths:
b.m
c.m
b.y
c.m
d.z

this command returns:
b.m
b.y
c.m
d.z
</pre>

