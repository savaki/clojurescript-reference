---
title: "Data Types"
active_tab: data-types
---
# ClojureScript Data Types

## Arrays (Vectors)

JavaScript:

```
  var values = [1, 2, 3, 4];
```

ClojureScript:

```
  (def values [1 2 3 4])
```

## Maps 

JavaScript:

```
  var params = {"hello": "world", "foo": "bar"};
```

ClojureScript:

```
  (def params { "hello" "world" 
                "foo" "bar" })
```

ClojureScript allows you to put commas where you would expect, but it's completely
optional and generally not used.  For clarity, it's best to put key/value pairs on their
own line.

## Sets 

A set is a collection with only unique elements.  JavaScript has no corresponding structure.

ClojureScript:

```
  (def params #{ "1" "2" "3"}) 
```

## Accessing Arrays (Vectors)

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

## Accessing Maps 

JavaScript:

```
  var params = {"hello": "world", "foo": "bar"};
  console.log(params["hello"]);
```

ClojureScript:

```
  (def params { "hello" "world" 
                "foo" "bar" })
  (println (params "hello")) ; prints hello                
  (println (params "does-not-exist")) ; prints nil                
```

ClojureScript allows you to put commas where you would expect, but it's completely
optional and generally not used.  For clarity, it's best to put key/value pairs on their
own line.

## Accessing Nested Maps 

JavaScript:

```
  var params = {
    "us": {"currency": "usd"},
    "jp": {"currency": "yen"}
  }
     
  console.log(params["us"]["currency"]); // prints usd
```

ClojureScript:

```
  (def params {
    "us" {"currency" "usd"}
    "jp" {"currency" "yen"}
  })

  (println (get-in params ["us" "currency"])) ; prints usd
```

get-in accepts a vector that allows you to traverse arbitrarily deep nested maps. 

## Accessing Nested Maps/Arrays 

Illustrates accessing complex objects that contain both maps and arrays.

JavaScript:

```
  var params = {
    "us": {"timezones": ["EST", "CST", "MST", "PST", "HST", "AKST"]},
    "jp": {"timezones": ["JST"]}
  }
     
  console.log(params["us"]["timezones"][2]]); // prints MST
```

ClojureScript:

```
  (def params {
    "us" {"timezones" ["EST" "CST" "MST" "PST" "HST" "AKST"]}
    "jp" {"timezones" ["JST"]}
  })

  (println (get-in params ["us" "timezones" 2])) ; prints MST
```

get-in accepts a vector that allows you to traverse arbitrarily deep nested maps. 

## Accessing Sets 

ClojureScript:

```
  (def params #{ "a" "b" "c"})
  (println (params "a")) ; prints a
  (println (params "d")) ; prints nil
```







