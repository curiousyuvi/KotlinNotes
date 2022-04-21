# KotlinNotes

- `print()` function is used to print without newLine while `println()` function is used to print with newLine

## Variables
   
   - `var` is used to decalare mutable variables
   Example: 
   ```kotlin
   var myName = "Hello"
   ```
    
   - `val` is used to declare immutable variables
   Example: 
   ```kotlin
   val x = 12
   ```
   
   - when using `var` it implicitly defines the type of variable by the value you pass, but we can also explicitly define types.
   - like so : 
   ```kotlin
   var name : String = "Hello" 
   ```
   - also when explicitly defining type we don't need to do initialization during declaration
   Example : 
   ```kotlin
   var x : Int
   x = 2
   ```
   
## Data Types

   - Integer data types - `Byte`, `Short`, `Int`, `Long`
   - In numeric literals we can add a `_` after every 3 digit to increase readability
   Example : 
   ```kotlin
   var num = 234_332_234
   ```
   
   - Floating point data types - `Float`, `Double`
   - The literal for floating type value have an `F` appended in end
   Example : 
   ```kotlin
   val f:Float = 32.12F
   ```
    
   - Boolean
   ```kotlin
   var flag:Boolean = true
   ```
   
   - Char
   ```kotlin
   var c:Char = 'a'
   ```
   
   - String
   ```kotlin
   var str:String = "abc"
   var n = str.length
   ```
   - Any

## String interpolation

  Example :
  ```kotlin
  val str = "guys"
  println("hello $str")
  println("n = ${str.length}")
  ```

## When statement
  - Similar to switch statement
  Example 1:
  ```kotlin
  var n = 1
  when(n){
  
   1 -> println("One")
   
   2 -> println("One")
   
   3 -> {
      println("Three")
      println("Three")
     }
     
   in 4..6 -> println("four to six")
   
   7, 9 -> println("seven or nine")
   
   !in 10..12 -> println("not ten to twelve")
   
   else -> println("none")
   
  }
  ```
  
  Example 2:
  ```kotlin
  var x: Any = 1.0
  when(n){
   
   is Int -> println("is Int")
   
   is Double -> println("is Double")
   
   else -> println("none")
   
  }
