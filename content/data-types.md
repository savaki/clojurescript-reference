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
  (println (params "hello"))                
```

ClojureScript allows you to put commas where you would expect, but it's completely
optional and generally not used.  For clarity, it's best to put key/value pairs on their
own line.

## Accessing Sets 

ClojureScript:

```
  (def params #{ "a" "b" "c"})
  (println (params "a")) ; prints a
  (println (params "d")) ; prints nil
```







