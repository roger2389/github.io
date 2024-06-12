# TEJ API

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Code Annotation Example

### Codeblock

some `codes` goes here

### Plain codeblock

A plain codeblock:

```py linenums="1"
Some code here
def myfunction()
// some comment
```

### Code for a specific language

Some more code with the `py` at the start:

```py linenums="1"
import tensorflow as tf
def whatever()
```

### With a title

```py title="bubble_sort.py" linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

### With line numbers

``` py linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

### Highlighting lines

```py linenums="1" hl_lines="2 3"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

## Icons and Emojs

:fontawesome-regular-face-laugh-wink:

:fontawesome-brands-twitter:{ .twitter }

:octicons-heart-fill-24:{ .heart }



