# spl-quiz
This repository contains set of questions for a self-check based on the book "The Swift Programming Language (Swift 3 beta)".

## A Swift Tour

Questions:

<details> 
  <summary>1. Do you need a main() funtion as an entry point for the programm in Swift?</summary>
  
  No, because global scope is used as an entry point itself.
</details>

### Simple Values

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

<details> 
  <summary>7. How do you create arrays and dictionaries? How do you access their elements?</summary>
  
```Swift
var colorsArray = ["red", "green", "blue"]
colorsArray[1] = "yellow"
var clothesDictionary = ["color": "blue", "size": "M"]
clothesDictionary["size"] = "L"
```
</details>

<details> 
  <summary>8. What will this code do?
```Swift
let const1 = [String]()
let const2 = [String: Float]()
```
  </summary>

  It will create an empty array of Strings and empty dictionary, which keys are Strings and values are Floats.
</details>

<details> 
  <summary>9. Can you use this code to create empty arrays and dictionaries?
```Swift
colorsArray = []
clothesDictionary = [:]
```
  </summary>

  Yes, but only if type information can be inferred.
</details>

### Control Flow

<details> 
  <summary>10. What is wrong with this code?
```Swift
var score = 1
if score print("Score isn't zero")
```
  </summary>

  Two things actually. First - in an **if** statement, the conditional must be a **Boolean** expression. Second - braces around the body are required. So, the code should look like this:
```Swift
var score = 1
if score > 0 {
  print("Score isn't zero")
}
```  
</details>

<details> 
  <summary>11. What does **?** after the type of value mean?
```Swift
var myString: String? = "Hello"
```
  </summary>

  It means that a value is optional, i.e. it will contain **nil** if value is missing. If you assign **nil** to a value, which isn't optional, compiler will give you an error.
</details>

<details> 
  <summary>12. How to unwrapp optional value in an **if** statement and make it available inside the block of code?</summary>

  You can use **if** and **let** keywords together to unwrapp a value. If the optional value is **nil**, the conditional is false and the code in braces is skipped.
  ```Swift
var optionalName: String? = "Bob"
if let name = optionalName {
  print("Hello, \(name)")
}
```
</details>

<details> 
  <summary>13. How to provide a default value when you work with optionals?</summary>

  You can provide default value using the **??** operator like this:
```Swift
let optionalName: String? = nil
print("Welcome, \(optionalName ?? "User")")
```
</details>

<details> 
  <summary>13. How to provide a default value when you work with optionals?</summary>

  You can provide default value using the **??** operator like this:
```Swift
let optionalName: String? = nil
print("Welcome, \(optionalName ?? "User")")
```
</details>

<details> 
  <summary>14. Can a **switch** statement contain more then one **case**, that match the value? If so, which one will be executed?</summary>

  Yes, it can. Switches support any kind of data and wide variety of comparison operations. For example, you can check if a value has full match with the other one in a **case** statement. Or check if it match with one of the listed options. Or check if it match the specific pattern you can specify with **let** and **where** keywords. If there are several cases that match the value, only the first one will be executed.
</details>
