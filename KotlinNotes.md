# KotlinNotes

## Variables
   
   -`var` is used to decalare mutable variables
    Example: `var myName = "Hello"`
    
   - `val` is used to declare immutable variables
   Example: `val x = 12`
   
   - when using `var` it implicitly defines the type of variable by the value you pass, but we can also explicitly define types.
   - like so : `var name : String = "Hello" `
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
    
    