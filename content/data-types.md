---
title: "Data Types"
active_tab: data-types
---
# ClojureScript Data Types

## Data Types

### Arrays (vectors)

JavaScript:

```
  var values = [1, 2, 3, 4];
```

ClojureScript:

```
  (def values [1 2 3 4])
```

### Maps 

JavaScript:

```
  var params = {"hello": "world",
                "foo": "bar"};
```

ClojureScript:

```
  (def params { "hello" "world" 
                "foo" "bar" })
```

ClojureScript allows you to put commas where you would expect, but it's completely
optional and generally not used.  For clarity, it's best to put key/value pairs on their
own line.

### Sets 

A set is a collection with only unique elements.  JavaScript has no corresponding structure.

ClojureScript:

```
  (def params #{ "1" "2" "3"}) 
```

## Accessing Data Types

### Accessing arrays (vectors)

JavaScript:

```
  var values = [1, 2, 3, 4];
  console.log(values[0]);  // prints 1
```

ClojureScript:

```
  (def values [1 2 3 4])
  (println (values 0)) ; prints 1
  (println (values 100)) ; prints nil
```

### Accessing maps 

JavaScript:

```
  var params = {"hello": "world",
                "foo": "bar"};
  console.log(params["hello"]);
```

ClojureScript:

```
  (def params { "hello" "world" 
                "foo" "bar" })

  ; prints hello                
  (println (params "hello")) 
  
  ; prints nil
  (println (params "does-not-exist"))                 
```

ClojureScript allows you to put commas where you would expect, but it's completely
optional and generally not used.  For clarity, it's best to put key/value pairs on their
own line.

### Accessing nested maps 

JavaScript:

```
  var params = {
    "us": {"currency": "usd"},
    "jp": {"currency": "yen"}
  }
     
  // prints usd
  console.log(params["us"]["currency"]); 
```

ClojureScript:

```
  (def params {
    "us" {"currency" "usd"}
    "jp" {"currency" "yen"}
  })

  ; prints usd
  (println (get-in params ["us" "currency"])) 
```

get-in accepts a vector that allows you to traverse arbitrarily deep nested maps. 

### Accessing nested maps/arrays 

Illustrates accessing complex objects that contain both maps and arrays.

JavaScript:

```
  var params = {
    "us": {"timezones": ["EST", 
                         "CST", 
                         "MST", 
                         "PST", 
                         "HST", 
                         "AKST"]},
    "jp": {"timezones": ["JST"]}
  }
     
  // prints MST     
  console.log(params["us"]["timezones"][2]]); 
```

ClojureScript:

```
  (def params {
    "us" {"timezones" ["EST" 
                       "CST" 
                       "MST" 
                       "PST" 
                       "HST" 
                       "AKST"]}
    "jp" {"timezones" ["JST"]}
  })

  ; prints MST
  (println (get-in params ["us" "timezones" 2])) 
```

get-in accepts a vector that allows you to traverse arbitrarily deep nested maps. 

### Accessing sets 

ClojureScript:

```
  (def params #{ "a" "b" "c"})
  (println (params "a")) ; prints a
  (println (params "d")) ; prints nil
```

## Manipulating Collections

### map

map takes a collection of items and applies a function to each
elements and returns the resulting collection.

```
(def numbers [2 3 5 7])

; square each element
(def square (fn [x] (* x x)))

; square in shorthand notation
(def square #(* % %))

; returns (4 9 25 49)
(map square numbers)
```

Notice that a set is returned. To convert this into an array
you can do the following:

```
(vec (map square numbers))
```

### filter

filter takes a collections and a applies a function over each
element and returns the set of elements where the function
returned true.

```
(def values [1 2 3 4 5 6])

(def is-odd? #(= (mod % 2) 1))

; returns (1 3 5)
(filter is-odd? values)
```

Another example:

```
(def greater-than-two? #(> % 2))

; returns (3 4 5 6)
(filter greater-than-two? values)
```

### reduce

Apply an aggregating function to a collection to return a
single scalar value.

```
(def values [1 2 3 4])

; returns 10 
; e.g. (((1 + 2) + 3) + 4)
(reduce + values)

; returns 24 
; e.g. (((1 * 2) * 3) * 4)
(reduce * values)

; also returns 10 using a custom
; function.   
(defn plus [a b] (+ a b))
(reduce plus values)
```








