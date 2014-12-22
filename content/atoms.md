---
title: "Atoms"
active_tab: atoms
---
# Working With Atoms

To store state in a ClojureScript atom, you must declare an atom.  

## Basic Usage

An atom is a container that represents state within an application.    

```
(def my-name (atom "Matt"))

(println my-name) ; prints the atom itself, #<Atom: matt>
(println @my-name) ; prints the contents of the atom, "Matt"                                            
```

One common confusion is to reference the atom versus the contents of the atom.
Remember to use the ```@``` symbol to reference the contents of the atom.

### reset! - setting state 

```
(def counter-state (atom 1))

(reset! counter-state 2) ; @counter-state is now 2
```

The reset! command throws out the previous value of the atom and resets it to the
value provided.

### swap! - updating values 

```
(def counter-state (atom 1))

(swap! counter-state (fn [n] (+ n 1))) ; @counter-state is now 2
```

swap! a) takes the existing state, b) passes it to a function, and c) assigns
the value of the atom to the value returned by the function.

We could also have written the example as follows:

```
(defn plus-one [n]
  (+ 1 n))
  
(swap! counter-state plus-one) ; uses our custom function, plus-one
(swap! counter-state inc) ; uses the clojurescript built-in function, inc
```

```inc``` is a function that takes one argument and returns its value plus one. 

### swap! - updating nested values 

JavaScript:

```
var data = {
  'us': { 'currency': 'usd' },
  'jp': { 'currency': 'yen' }
};

data['us']['currency'] = '$';
```

ClojureScript:

```
(def data {
  'us' { 'currency' 'usd' }
  'jp' { 'currency' 'yen' }
})

; changes currency from usd to $
(swap! data assoc-in ['us' 'currency'] "$") 
```

In this case, we're using the assoc-in function to accept data and return a new
map with ```['us' 'currency']``` modified with ```$``` 

