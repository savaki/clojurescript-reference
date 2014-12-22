---
title: "Basic Usage"
active_tab: basic-usage
---
# Basic Usage

## Working with strings

### println

JavaScript:

```
console.log("hello world, " + 123);
```

ClojureScript:

```
; called to enable printing to console.log
(enable-console-print!)

(println "hello world, " 123)
```

### str

appends strings together

JavaScript:

```
first + " " + last;
```

ClojureScript:

```
(str first " " last)
```

## Math

### add, subtract, multiply, divide

```
; returns 3 
(+ 1 2)

; returns 6
(+ 1 2 3)

; returns 1
(- 6 5)

; returns -6
; (((6 - 5) - 4) - 3)
(- 6 5 4 3)

; returns 2
(* 1 2)

; returns 6
(* 1 2 3)

; returns 2
(/ 6 3)

; returns 1
(/ 6 3 2)
```

add, subtract, multiple, and divide will all take two or
more arguments and successive apply the specified operation
across all the arguments provided.

### modulus

; returns 2
(mod 5 3)

## Functions

### defn - named functions

JavaScript:

```
function helloWorld(arg1, arg2) {
  console.log(arg1 + arg2);
}
```

ClojureScript:

```
(defn hello-world [arg1 arg2]
  (println arg1 arg2))
```

### fn - anonymous functions

JavaScript:

```
function(arg1) {
  console.println("arg1 = " + arg1); 
}
```

ClojureScript:

```
(fn [arg1] (println "arg1 = " arg1)) 
```

### #() - shorthand anonymous functions

Since anonymous functions are called
so often, there is a shorthand notation
for them, #().

JavaScript:

```
function(arg1) {
  console.println("arg1 = " + arg1); 
}
```

ClojureScript:

```
#(println %)
```

% is a placeholder for the first 
argument similar to _ in Scala and $_
in perl.

### #() with multiple args

Sometimes we need anonymous functions
to access more than one variable:

JavaScript:

```
function(first, last) {
  console.println(first + " " + last);
}
```

ClojureScript:

```
#(println %1 " " %2)
```

%1 indicates the first argument, %2 the
second, and so on and so forth.

## Temporary variables

### let 

JavaScript:

```
function sample() {
  var first = "Matt";
  var last = "Matt";
  console.println(last + "," + first);
}
```

ClojureScript:

```
(defn sample []
  (let [first "Matt"
        last "Ho"]
    (println last "," first)))
```

Let allows you to create temporary
variables that are scoped to the let
statement.




