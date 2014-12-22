---
title: "Reagent"
active_tab: reagent
---
# Reagent

## Basic Usage

### Creating a component

```
(defn salutations []
  [:div.content
    [:p#name "hello world"]
  ])
  
```

renders:

```
<div class="content">
  <p id="name">hello world</p>
</div>  
```

### Composing components

```
(defn greetings [name]
  [:div.content
    [:p#name "Hello " name]
  ])
  
(defn composed-component []
  [:div.parent
    [greetings "Matt"]
  ])
  
```

```composed-component``` renders:

```
<div class="parent">
  <div class="content">
    <p id="name">Hello Matt</p>
  </div>
</div>
```

### Iterating arrays

```
(defn week-day [day]
  [:th day])

(defn week-days []
  (let [days ["Sun" "Mon" "Tue" "Wed" "Thu" "Fri" "Sat"]
    [:tr
      (for [day days]
        [week-day day])
    ]))
```

renders:

```
<tr>
  <td>Sun</td>
  <td>Mon</td>
  <td>Tue</td>
  <td>Wed</td>
  <td>Thu</td>
  <td>Fri</td>
  <td>Sat</td>
</tr>
```

```
```
