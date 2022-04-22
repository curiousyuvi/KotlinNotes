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
  - Example 1:
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
  
  - Example 2:
  ```kotlin
  var x: Any = 1.0
  when(n){
   
   is Int -> println("is Int")
   
   is Double -> println("is Double")
   
   else -> println("none")
   
  }
  ```

## For loop

  - Example 1 :
  ```kotlin
  for(num in 1..10){
   print("$num ")
  }
  ```
  Output :  1 2 3 4 5 6 7 8 9 10
  
  - Example 2 :
  ```kotlin
  for(num in 1 until 10){
   print("$num ")
  }
  ```
  Output :  1 2 3 4 5 6 7 8 9
  
  - Example 3 :
  ```kotlin
  for(num in 10 downTo 1){
   print("$num ")
  }
  ```
  Output :  10 9 8 7 6 5 4 3 2 1
  
  - Example 4 :
  ```kotlin
  for(num in 1 until 10 step 2){
   print("$num ")
  }
  ```
  Output :  1 3 5 7 9


## Function

  - Example 1:
  ```kotlin
  fun greet(name: String){
   println("Hello $name")
  }
  ```
  - Example 2:
  ```kotlin
  fun add(a:Int,b:Int): Int{
   return a+b
  }
  ```
  
  - Anonymous function example:
  ```kotlin
  var f = fun(a:Int,b:Int): Int{
   return a+b
  }
  
  println(f(1,3))
  ```
  - Lambda function example:
  ```kotlin
  var f = {a:Int,b:Int -> a+b}
  
  println(f(1,3))
  ```

## Nullables
   
   - Types which also accept null values
   - Add `?` at the end of type to make nullable type
   - Example:
   ```kotlin
   var nullableName:String?
   nullableName = null
   
   // if nullableName is not null store its length in null, else store null in len
   var len = nullableName?.length
   
   // execute the code only if value is not null
   nullableName?.Let {println(it.length)}
   
   // ?: Elvis Operator
   // if nullableName is not null store it in name, else store some default value
   val name = nullableName ?: "John Doe"
   
   // !! Not null assertion operator
   // it converts a nullable type to not nullable type and throws null exception if used on null
   val name2 = nullableName!!
   
   ```
   
## Classes
   - Example 1:
   ```kotlin
   fun main(){
      var jacob = Person(firstName = "Jacob", lastName = "Maer")
   }
   
   class Person(firstName: String, lastName: String){
      init {
         println("Initalized a new person with firstName = $firstName and lastName = $lastName")
      }  
   }
   ```
   - Example 2:
   ```kotlin
   fun main(){
      var jacob = Person(firstName = "Jacob", lastName = "Maer")
      var john = Person()
   }
   
   class Person(firstName: String = "John", lastName: String = "Doe"){
      init {
         println("Initalized a new person with firstName = $firstName and lastName = $lastName")
      }
   }
   ```
   
   - Example 3:
   ```kotlin
   fun main(){
      var jacob = Person(firstName = "Jacob", lastName = "Maer")
      jacob.stateHobby()
      jacob.hobby = "stealing"
      jacob.stateHobby()
   }
   
   class Person(firstName: String = "John", lastName: String = "Doe"){
      
      // member variables
      var hobby:String = "playing soccer"
      
      init {
         println("Initalized a new person with firstName = $firstName and lastName = $lastName")
      }
      
      // member fuction
      fun stateHobby(){
         println("My hobby is to $hobby)
      }
   }
   ```
   
   - Example 4:
   ```kotlin
   fun main(){
      var jacob = Person(firstName = "Jacob", lastName = "Maer", age = 19)
      jacob.stateAge()
   }
   
   class Person(firstName: String = "John", lastName: String = "Doe"){
      
      // member variables
      var age : Int? = null
      
      // secondary member constructor
      constructor(firstName : String, lastName : String, age : Int) : this(firstName,lastName){
         this.age = age
         println("Initalized a new person with firstName = $firstName, lastName = $lastName and age = $age")
      }
      
      init {
         println("Initalized a new person with firstName = $firstName and lastName = $lastName")
      }
      
      // member fuction
      fun stateAge(){
         println("My age is $age)
      }
   }
   ```
   
   - We can't acces parameters from Primary constructor in member functions, so we have to create member varible to store them

   - Example 5:
   ```kotlin
   fun main(){
      var jacob = Person(firstName = "Jacob", lastName = "Maer", age = 19)
      jacob.stateAge()
   }
   
   class Person(firstName: String = "John", lastName: String = "Doe"){
      
      // member variables
      var age : Int? = null
      var firstName : String? = null
      
      // secondary member constructor
      constructor(firstName : String, lastName : String, age : Int) : this(firstName,lastName){
         this.age = age
         println("Initalized a new person with firstName = $firstName, lastName = $lastName and age = $age")
      }
      
      init {
         println("Initalized a new person with firstName = $firstName and lastName = $lastName")
         this.firstName= firstName
      }
      
      // member fuction
      fun stateAge(){
         println("$firstName \'s age is $age)
      }
   }
   ```
   
   - By default kotlin has getter and setter like this :
   ```kotlin
   get() = field
   set(value){
      field = value
   }
   ```
   
   - We can also write custom getter and setter
   ```kotlin
   fun main(){
      var jacob = Person(firstName = "Jacob", lastName = "Maer", age = 19)
      println("${jacob.firstName} \'s age is ${jacob.age}")
      jacob.age = 12;
      println("${jacob.firstName} \'s age is ${jacob.age}")
      
   }
   
   class Person(firstName: String = "John", lastName: String = "Doe"){
      
      // member variables
      var age : Int? = null
         // custom getter and setter
         get() {
            return field?.plus(4)
         }
         
         set(value) {
            field = value ?: 10
         }
      var firstName : String? = null
      
      // secondary member constructor
      constructor(firstName : String, lastName : String, age : Int) : this(firstName,lastName){
         this.age = age
         println("Initalized a new person with firstName = $firstName, lastName = $lastName and age = $age")
      }
      
      init {
         println("Initalized a new person with firstName = $firstName and lastName = $lastName")
         this.firstName= firstName
      }
   }
   ```
   
   - `private get` is used to make getter private
   - `private set` is used to make setter private

   - Data Class
   - Example :
   ```kotlin
   fun main(){
      val user1 = User(122,"John")
      println(user1)
      val user2 : User = user1.copy(name = "Michael")
      
      println(user2.component1())
      println(user2.component2())
      
      var (id,name) = user1
      println(id)
      println(name)
      
      
   }
   
   data class User(val id: Long, var name : String)
   ```
