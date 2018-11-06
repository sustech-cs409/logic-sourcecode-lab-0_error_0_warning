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


$$
\begin{align*}
p &= a \and b \and (c \or d) \\

p_a &= p_{a=true} \oplus p_{a=false} \\
&=(true \and b \and (c \or d))\oplus(false \and b \and (c \or d)) \\
&= (b \and (c \or d)) \oplus false \\
&= b \and (c \or d) \\

p_b &= p_{b=true} \oplus p_{b=false} \\
&= (a \and true \and (c \or d)) \oplus (a \and false \and (c \or d)) \\
&= (a \and (c \or d)) \oplus false \\
&= a \and (c \or d) \\

p_c &= p_{c=true} \oplus p_{c=false} \\
&= (a \and b \and (true \or d)) \oplus (a \and b \and (false \or d)) \\
&= (a \and b) \oplus (a \and b \and d) \\
&= (a \and b) \oplus d\\

p_d &= p_{d=true} \oplus p_{d=false} \\
&= (a \and b) \oplus c



\end{align*} \\
$$






