# Ch8 lab2

```java
if (value.length() > checklistpos + 2 && value.charAt(checklistpos + 2) == ']' && (checklistpos == 0 || value.charAt(checklistpos - 1) == '\n'))
```

```
a: value.length() > checklistpos + 2
b: value.charAt(checklistpos + 2) == ']'
c: checklistpos == 0
d: value.charAt(checklistpos - 1) == '\n'
```

```
a && b && (c || d)
```

## Predicate Coverage

```
p = a && b && (c || d)
```

Make p = true

* a=true, 
* b=true, 
* c=true, 
* d=false

Make p = false

* a=false,
* b=false,
* c=true
* d=true

## Clause Coverage

```
p = a && b && (c || d)
```

1. a=true, b=false, c=true, d=true;
2. a=false, b=true, c=false, d=false.

## Combinatorial Coverage

```
p = a && b && (c || d)
```

|      | a    | b    | c    | d    | a && b && (c \|\| d) |
| ---- | ---- | ---- | ---- | ---- | -------------------- |
| 1    | T    | T    | T    | T    | T                    |
| 2    | T    | T    | T    | F    | T                    |
| 3    | T    | T    | F    | T    | T                    |
| 4    | T    | T    | F    | F    | F                    |
| 5    | T    | F    | T    | T    | F                    |
| 6    | T    | F    | T    | F    | F                    |
| 7    | T    | F    | F    | T    | F                    |
| 8    | T    | F    | F    | F    | F                    |
| 9    | F    | T    | T    | T    | F                    |
| 10   | F    | T    | T    | F    | F                    |
| 11   | F    | T    | F    | T    | F                    |
| 12   | F    | T    | F    | F    | F                    |
| 13   | F    | F    | T    | T    | F                    |
| 14   | F    | F    | T    | F    | F                    |
| 15   | F    | F    | F    | T    | F                    |
| 16   | F    | F    | F    | F    | F                    |



## Correlated Active Clause Coverage

```
p = a && b && (c || d)
```


<a href="https://www.codecogs.com/eqnedit.php?latex=p_a&space;&=&space;p_{a=true}&space;\oplus&space;p_{a=false}&space;\\&space;&=(true&space;\wedge&space;b&space;\wedge&space;(c&space;\vee&space;d))\oplus(false&space;\wedge&space;b&space;\wedge&space;(c&space;\vee&space;d))&space;\\&space;&=&space;(b&space;\wedge&space;(c&space;\vee&space;d))&space;\oplus&space;false&space;\\&space;&=&space;b&space;\wedge&space;(c&space;\vee&space;d)&space;\\&space;p_b&space;&=&space;p_{b=true}&space;\oplus&space;p_{b=false}&space;\\&space;&=&space;(a&space;\wedge&space;true&space;\wedge&space;(c&space;\vee&space;d))&space;\oplus&space;(a&space;\wedge&space;false&space;\wedge&space;(c&space;\vee&space;d))&space;\\&space;&=&space;(a&space;\wedge&space;(c&space;\vee&space;d))&space;\oplus&space;false&space;\\&space;&=&space;a&space;\wedge&space;(c&space;\vee&space;d)&space;\\" target="_blank"><img src="https://latex.codecogs.com/svg.latex?p_a&space;&=&space;p_{a=true}&space;\oplus&space;p_{a=false}&space;\\&space;&=(true&space;\wedge&space;b&space;\wedge&space;(c&space;\vee&space;d))\oplus(false&space;\wedge&space;b&space;\wedge&space;(c&space;\vee&space;d))&space;\\&space;&=&space;(b&space;\wedge&space;(c&space;\vee&space;d))&space;\oplus&space;false&space;\\&space;&=&space;b&space;\wedge&space;(c&space;\vee&space;d)&space;\\&space;p_b&space;&=&space;p_{b=true}&space;\oplus&space;p_{b=false}&space;\\&space;&=&space;(a&space;\wedge&space;true&space;\wedge&space;(c&space;\vee&space;d))&space;\oplus&space;(a&space;\wedge&space;false&space;\wedge&space;(c&space;\vee&space;d))&space;\\&space;&=&space;(a&space;\wedge&space;(c&space;\vee&space;d))&space;\oplus&space;false&space;\\&space;&=&space;a&space;\wedge&space;(c&space;\vee&space;d)&space;\\" title="p_a &= p_{a=true} \oplus p_{a=false} \\ &=(true \wedge b \wedge (c \vee d))\oplus(false \wedge b \wedge (c \vee d)) \\ &= (b \wedge (c \vee d)) \oplus false \\ &= b \wedge (c \vee d) \\ p_b &= p_{b=true} \oplus p_{b=false} \\ &= (a \wedge true \wedge (c \vee d)) \oplus (a \wedge false \wedge (c \vee d)) \\ &= (a \wedge (c \vee d)) \oplus false \\ &= a \wedge (c \vee d) \\" /></a>







