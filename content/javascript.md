---
title: "JavaScript"
active_tab: javascript
---
# Working With JavaScript

## Basic Usage

### Accessing vars

Given:

``` 
  var name = "Matt";
```

JavaScript:

``` 
  console.log(name)
```

ClojureScript

```
  (println js/name)
```

### Accessing object attributes

Given: 
 
```
  var person = {name: "Matt"}
```

JavaScript:

```
  console.log(person.name);
```

ClojureScript:

```
  (println (.-name js/person))
```

JavaScript object attributes are accessed via the .-{property} macro

### Invoking methods

JavaScript:

```
  document.getElementById("app")
```

ClojureScript:

```
  (.getElementById js/document "app")
```

### Invoking chained methods

JavaScript:

```
  document.getElementById("app").append(element);
```
                    
ClojureScript:

```
  (.append (.getElementById js/document "app") element)
```

