---
icon: lucide/languages
---

# Languages, etc.

## Python

### Fundamentals

Please use the <a href="https://peps.python.org/pep-0008/">PEP (Python Enhancement Proposal) 8 Style Guide for
Python</a>.  Always refer to the naming conventions guide, for example:

<br>

<table style="width: 85%;">
    <colgroup>
        <col span="1" style="width: 26.5%;">
        <col span="1" style="width: 63.5%;">
    </colgroup>
    <thead><tr style="text-align: left"><th>Object</th><th>Note</th></tr></thead>
        <tr><td>Type Variable Name</td><td>Always pascal case, e.g., HyperParameter.</td></tr>
        <tr><td>Class Name</td><td>Always pascal case.</td></tr>
        <tr><td>Variable Name</td><td>A lower case or snake case string, e.g., <i>length</i>, `number_of_cities` Use two leading underscores for private variables.</td></tr>
        <tr><td>Constants</td><td>The PEP pages note that <a href="https://peps.python.org/pep-0008/#constants" target="_blank">constants</a> <q><i>... are usually defined on a 
module level and written in all capital letters with underscores separating words. Examples include MAX_OVERFLOW and TOTAL.</i></q></td></tr>
</table>

<br>

### Importing Modules

Abide by the [module importing advice](https://docs.python-guide.org/writing/structure/#modules) of the HitchHiker's Guide to Python, it is an excellent guide to Python software development best practices; beware of the readability advice.  Hence, please use the import format `import math`, and use a method of the module via the pattern

```python
import math

math.cos(...)
```

<b>not</b>

!!! note ""
    
    &nbsp; &nbsp; :fontawesome-solid-xmark:{ .lg .middle } `#!python from math import cos`
    
    &nbsp; &nbsp; :fontawesome-solid-xmark:{ .lg .middle } `#!python from math import *`



<br>

## Scala

The <a href="https://docs.scala-lang.org/style/" target="_blank">Scala Style Guide</a> will be the team's style reference. Take note of the naming conventions.  The names of classes, objects, methods, etc., are either pascal case, also known as
upper camel case, camel case, or lower case.  Names do not include underscores.

<br>

<table style="width: 85%;">
    <colgroup>
        <col span="1" style="width: 26.5%;">
        <col span="1" style="width: 63.5%;">
    </colgroup>
    <thead>
      <tr style="text-align: left"><th>Object</th><th>Note</th></tr></thead>
      <tr>
        <td><a href="https://docs.scala-lang.org/style/naming-conventions.html#classestraits" target="_blank">Classes/Traits</a></td>
        <td>Pascal Case</td></tr>
      <tr>
        <td><a href="https://docs.scala-lang.org/style/naming-conventions.html#objects" target="_blank">Objects</a></td>
        <td>Pascal Case</td></tr>
      <tr>
        <td>Packages</td>
        <td>In line with Java's packages naming conventions: <a href="https://www.baeldung.com/java-packages#1-naming-conventions" target="_blank">Baeldung</a>, <a href="https://www.javatpoint.com/java-naming-conventions#:~:text=code%20snippet%0A%7D-,Package,-It%20should%20be">javapoint</a></td></tr>
      <tr>
        <td><a href="https://docs.scala-lang.org/style/naming-conventions.html#constants-values-and-variables" target="_blank">Constants</a></td>
        <td>Pascal Case</td></tr>
</table>


<br>

## Shell

<a href="https://google.github.io/styleguide/shellguide.html" target="_blank">Refer to Google's Shell Style Guide</a>

<br>
<br>

<br>
<br>

<br>
<br>

<br>
<br>
