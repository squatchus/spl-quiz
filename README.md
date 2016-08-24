# spl-quiz
This repository contains set of tests for a self-check based on the book "The Swift Programming Language (Swift 3 beta)".

## A Swift Tour

Questions:

<details> 
  <summary>1. Do you need a main() funtion as an entry point for the programm in Swift?</summary>
  
  No, because global scope is used as an entry point itself.
</details>

<details> 
  <summary>2. How to declare constants and variables in Swift?</summary>
  
  You declare it with a keywords **let** and **var** like this:
```Swift
var myVariable = 42
let myConstant = 42
```
</details>

<details> 
  <summary>3. Do you have to assign the value of the constant, when you declare it?</summary>
  
  The value of a constant can be assigned later, but you must to assign it a value exactly once.
</details>

<details> 
  <summary>4. How do you specify the type of constant or variable?</summary>
  
  You write the type after it's name, separated by colon, like this:
```Swift
let explicitDouble: Double = 70
```
</details>

<details> 
  <summary>5. Will this code compile?
```Swift
let label = "The width is "
let width = 94
let widthLabel = label + width
```
</summary>

  No, because **label** and **width** have different types. You need to convert it explicitly, like this:
```Swift
let widthLabel = label + String(width)
```
</details>

<details> 
  <summary>6. What is the simpler way to include values in strings?</summary>
  
  You can use **\\()** inside the string and put some value or calculation in parenthesis, like this:
```Swift
let widthLabel = "The width is \(width) inches"
```
</details>
