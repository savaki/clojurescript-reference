---
title: "JavaScript"
active_tab: javascript
---
# Working With JavaScript

## Accessing vars

In general, JavaScript variables can be referenced using the js prefix.  

For example, the _name_ var from the following snippet:

``` 
<script type="text/javascript">
  var name = "Matt";
</script>
```

can be accessed as:

```
js/name
```

e.g.

``` clojure
(println js/name)
```

## Accessing object attributes

Often, we want to access an attribute of a variable.  Given the following:
 
```
<script type="text/javascript">
  var person = {name: "Matt"}
</script>
```

We can access this via:

```
(.-name js/person)
```

_js/person_ references the variable, person, and  .-name tells ClojureScript you want to
access the attribute, name.

For example:

```
(println "hello " (.-name js/person))
```

## Invoking methods

Calling a method is similar to access an attribute.  Suppose we want to invoke:

```
document.getElementById("app")
```

We would write:

```
(.getElementById js/document "app")
```

If we take a moment and remove the punctuation, we see that JavaScript references values
as follows:

```
object function args ...
```

In ClojureScript, we simply reverse that to:

```
function object args ...
```

And apply the appropriate language syntax.  

Here's another example:
 
```
<script type="text/javascript">
var example = { 
  greeting: function(name) {
    console.log("hello " + name);
  }
};
</script>
```

We can invoke the greeting method from ClojureScript as follows:

```
(.greeting js/example "Matt")
```

The same in JavaScript would have been:

```
example.greeting("Matt")
```