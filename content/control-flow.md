---
title: "Control Flow"
active_tab: control-flow
---
# ClojureScript Control Flow

## Conditionals

### ==, >, >=, <, and <=

JavaScript

```
1 == 0; // false
1 > 0;  // true
1 >= 0; // true
1 < 0;  // false
1 <= 0; // false
```

ClojureScript:

```
(= 1 0)  ; false
(> 1 0)  ; true
(>= 1 0) ; true
(< 1 0)  ; false
(<= 1 0) ; false
```

### if 

JavaScript:

```
if( true ) {
  console.log("i am true");
} else {
  console.log("i am false");
}
```

ClojureScript:

```
(if true 
  println("i am true") 
  println("i am false"))
```

### cond e.g. if/else-if/else

JavaScript:

```
if( 2 > 3 ) {
  console.log("nope");
} else if (3 > 5) {
  console.log("no");
} else {
  console.log("yep");
}
```

ClojureScript:

```
(cond (> 2 3) (println "nope")
      (> 3 5) (println "no")
      :else   (println "yep"))
```

For if/else if/else statements, ClojureScript introduces a new function, cond.

## Logical Operators
      
### not
      
```
; returns false      
(not (true))
      
; also returns false
(not (> 1 2))      
```

### and

```
; returns false      
(and false true)

; returns true
(and true true)

; also returns true
(and (> 2 1) (> 5 4))
```

### or

```
; returns true
(or true false)

; returns false
(or false false)

; returns true
(or (> 2 1) (> 1 2))
```







