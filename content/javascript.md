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

### aget - simpler attribute getter

aget provides a simpler way to access nested javascript attributes

```
; object["p1"]["p2"]["p3"]
(aget js/object "p1" "p2" "p3")
```

### Setting object attributes

Given: 
 
```
  var person = {name: "Matt"}
```

JavaScript:

```
  person.name = "Mike";
```

ClojureScript:

```
  (set! (.-name js/person) "Mike)
```

JavaScript object attributes are accessed via the .-{property} macro

### aset - simple object attribute getter

aset provides an alternate way to set attributes on javascript objects

```
; window.location = "http://www.google.com")
(aset js/location "location" "http://www.google.com")
```

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

## Working with the browser

### document.location = ...

```
(def url "https://google.com")
(set! (.-location js/document) url)
```

### document.getElementById(...)

```
(.getElementById js/document "element-id")
```

### window.addEventListener(...)

```
(.addEventListener js/window "scroll" #(println %) false)
```

## Cookbook

### Capturing the escape key

```
; capture escape key
(defn handle-escape-key [event]
  (let [key-code (.-keyCode event)]
    (if (= key-code 27) (println "escape key pressed"))))
    
; register event listener    
(.addEventListener js/document "keyup" handle-escape-key)
```
