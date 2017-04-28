# spl-quiz
This repository contains set of questions for a self-check based on the book "The Swift Programming Language (Swift 3 beta)".

## Table of Contents
* [A Swift Tour](../master/README.md#a-swift-tour)
* [- Simple Values](../master/README.md#simple-values)
* [- Control Flow](../master/README.md#control-flow)
* [- Functions and Closures](../master/README.md#functions-and-closures)
* [- Objects and Classes](../master/README.md#objects-and-classes)


## A Swift Tour

1. Do you need a main() funtion as an entry point for the programm in Swift?
   <details> 
   <summary>Answer:</summary>
   
   No, because global scope is used as an entry point itself.
   </details>

### Simple Values

2. How to declare constants and variables in Swift?
   <details> 
   <summary>Answer:</summary>
  
   You declare it with a keywords **let** and **var** like this:
   ```Swift
   var myVariable = 42
   let myConstant = 42
   ```
   </details>
3. Do you have to assign the value of the constant, when you declare it?
   <details> 
   <summary>Answer:</summary>
  
   The value of a constant can be assigned later, but you must to assign it a value exactly once.
   </details>
4. How do you specify the type of constant or variable?
   <details> 
   <summary>Answer:</summary>
  
   You write the type after it's name, separated by colon, like this:
   ```Swift
   let explicitDouble: Double = 70
   ```
   </details>
5. Will this code compile?
   ```Swift
   let label = "The width is "
   let width = 94
   let widthLabel = label + width
   ```
   <details> 
   <summary>Answer:</summary>

   No, because **label** and **width** have different types. You need to convert it explicitly, like this:
   ```Swift
   let widthLabel = label + String(width)
   ```
   </details>
6. What is the simpler way to include values in strings?
   <details> 
   <summary>Answer:</summary>
  
   You can use **\\()** inside the string and put some value or calculation in parenthesis, like this:
    ```Swift
    let widthLabel = "The width is \(width) inches"
    ```
    </details>
7. How do you create arrays and dictionaries? How do you access their elements?
   <details> 
   <summary>Answer:</summary>

   ```Swift
   var colorsArray = ["red", "green", "blue"]
   colorsArray[1] = "yellow"
   var clothesDictionary = ["color": "blue", "size": "M"]
   clothesDictionary["size"] = "L"
   ```
   </details>
8. What will this code do?
   ```Swift
   let const1 = [String]()
   let const2 = [String: Float]()
   ```
   <details> 
   <summary>Answer:</summary>

   It will create an empty array of Strings and empty dictionary, which keys are Strings and values are Floats.
   </details>
9. Can you use this code to create empty arrays and dictionaries?
   ```Swift
   colorsArray = []
   clothesDictionary = [:]
   ```
   <details> 
   <summary>Answer:</summary>

   Yes, but only if type information can be inferred.
   </details>

### Control Flow

10. What is wrong with this code?
    ```Swift
    var score = 1
    if score print("Score isn't zero")
    ```
    <details> 
    <summary>Answer:</summary>

    Two things actually. First - in an **if** statement, the conditional must be a **Boolean** expression. Second - braces around the body are required. So, the code should look like this:
    ```Swift
    var score = 1
    if score > 0 {
      print("Score isn't zero")
    }
    ```  
    </details>
11. What does **?** after the type of value mean?
    ```Swift
    var myString: String? = "Hello"
    ```
    <details> 
    <summary>Answer:</summary>

    It means that a value is optional, i.e. it will contain **nil** if value is missing. If you assign **nil** to a value, which isn't optional, compiler will give you an error.
    </details>
12. How to unwrapp optional value in an **if** statement and make it available inside the block of code?
    <details> 
    <summary>Answer:</summary>

    You can use **if** and **let** keywords together to unwrapp a value. If the optional value is **nil**, the conditional is false and the code in braces is skipped.
    ```Swift
    var optionalName: String? = "Bob"
    if let name = optionalName {
      print("Hello, \(name)")
    }
    ```
    </details>
13. How to provide a default value when you work with optionals?
    <details> 
    <summary>Answer:</summary>

    You can provide default value using the **??** operator like this:
    ```Swift
    let optionalName: String? = nil
    print("Welcome, \(optionalName ?? "User")")
    ```
    </details>
14. Can a **switch** statement contain more then one **case**, that match the value? If so, which one will be executed?
    <details> 
    <summary>Answer:</summary>

    Yes, it can. Switches support any kind of data and wide variety of comparison operations. For example, you can check if a value has full match with the other one in a **case** statement. Or check if it match with one of the listed options. Or check if it match the specific pattern you can specify with **let** and **where** keywords. If there are several cases that match the value, only the first one will be executed.
    </details>
15. How do you iterate over items in a dictionary?
    <details> 
    <summary>Answer:</summary>

    One of the ways to do it is to use **for-in** statement, by providing a pair of names to use for each key-value pair:
    ```Swift
    let dict = ["key1": "value1", "key2": "value2"]
    for (key, value) in dict {
      print("key: \(key), value: \(value)")
    }
    ```
    </details>
16. Swift has several operators to make loops. Which one ensures, that the loop will run at least once?
    <details> 
    <summary>Answer:</summary>

    ```Swift
    repeat {
      print("This string will be printed at least once")
    } while false
    ```
    </details>
17. How do you iterate an index over a range?
    <details> 
    <summary>Answer:</summary>

    Use **..<** in a for-in loop to make a range that omits its upper value, and use **...** to make a range, that includes both values.
    ```Swift
    for i in 0..<5 {  // or 'for i in 0...5 {'
        print("index is: \(i)")
    }
    ```
    </details>

### Functions and Closures

18. How do you declare and call a function in Swift?
    <details> 
    <summary>Answer:</summary>

    Use **func** to declare a function. Call a function by following its name with a list of arguments in parentheses. Use **->** to separate parameter names and types from the function's return type.
    ```Swift
    func greet(person: String, day: String) -> String {
      return "Hello \(person), today is \(day)."
    }
    greet(person: "Bob", day: "Tuesday")
    ```
    </details>
19. How to modify a function from the answer to previous question, so that you can call it like this:
    ```Swift
    greet("Jhon", on: "Wednesday")
    ```
    <details> 
    <summary>Answer:</summary>

    By default, functions use their parameter names as labels for their arguments. Write **_** to use no **person** argument label and write a custom label **on** before **day** parameter name:
    ```Swift
    func greet(_ person: String, on day: String) -> String {
      return "Hello \(person), today is \(day)."
    }
    ```
    </details>
20. How to declare a function, that returns multiple values as a tuple? How to access the elements of a tuple?
    <details> 
    <summary>Answer:</summary>
  
    The elements of a tuple can be referred to either by name, or by number. A function, that returns a tuple can be declared like this:
    ```Swift
    func statsFor(array: [Int]) -> (min: Int, max: Int) {
      var min = array[0]
      var max = array[0]
      //...
      return (min, max)
    }
    let stats = statsFor(array: [1,2,3])
    print("min: \(stats.min), max: \(stats.1)")
    ```
    </details>
21. How to declare a function, that takes a variable number of arguments?
    <details> 
    <summary>Answer:</summary>
  
    Functions, that take a variable number of arguments, collect them into array. This kind of functions can be declared using **...** after the type:
    ```Swift
    func sumOf(numbers: Int...) -> Int {
      var sum = 0
      //...
      return sum
    }
    sumOf()
    sumOf(numbers: 1, 2, 3)
    ```
    </details>
22. Does nested functions have access to variables that were declared in the outer functions?
    <details> 
    <summary>Answer:</summary>
  
    Yes.
    </details>
23. How to declare a function that returns the following function as it's value?
    ```Swift
    func nestedFunc(argument: Int) -> Int {
      return argument*2
    }
    ```
    <details> 
    <summary>Answer:</summary>
  
    ```Swift
    func funcThatReturnsFunc() -> ((Int) -> Int) {
      func nestedFunc(argument: Int) -> Int {
        return argument*2
      }
      return nestedFunc
    }
    ```  
    </details>
24. How to declare a function that takes the following function as an argument?
    ```Swift
    func argumentFunc(argument: Int) -> Int {
      return argument*2
    }
    ```
    <details> 
    <summary>Answer:</summary>

    ```Swift
    func funcThatTakes(function: ((Int) -> Int)) -> Bool  {
      function(2)
      return true
    }
    ```
    </details>
25. How do you separate an arguments and return type from a body of closure?
    <details> 
    <summary>Answer:</summary>
  
    You separate it using **in** keyword before body.
    ```Swift
    numbers.map({
      (number: Int) -> Int in
      return number*2
    })
    ```
    </details>
26. In which case you can omit the parentheses in a function call like the one below? What does $0 and $1 mean?
    ```Swift
      let sortedNumbers = numbers.sorted { $0 > $1 }
    ```
    <details> 
    <summary>Answer:</summary>
  
    You can omit the parentheses of a function if closure is the only argument to it. $0 and $1 means you refer parameters of a closure by number instead of by name.
    </details>

### Objects and Classes

27. How do you declare a class with custom initializer, properties and methods? How do you create an instance of this class using custom initializer?
    <details> 
    <summary>Answer:</summary>
  
    You declare a class using **class** keyword and add an initialzer to it with **init** keyword like this:
    ```Swift
    class Person {
      var name: String
      var age: Int = 0
      init(name: String, age: Int) {
        self.name = name  // use 'self' to distinguish class property
        self.age = age    // from initializer argument with the same name
      }
      func description() -> String {
        return "\(name), \(age)"
      }
    }
    // create an instance using custom initializer like this:
    var person = Person(name: "Bob", age: 42)
    person.description()
    ```
    </details>
28. Will this code compile?
    ```Swift
    class User {
      var role: String = "User"
      var user_id: Int
      init(role: String) {
        self.role = role
      }
    }
    ```
    <details>
    <summary>Answer:</summary>
  
    No, because of __user_id__ property. Every property needs a value assigned - either in declaration (role) or in the initializer (user_id).
    </details>
