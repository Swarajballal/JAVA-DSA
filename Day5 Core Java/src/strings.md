### Strings

```java

package org.studyeasy;

public class App {

	public static void main(String[] args) {
		String x = "Study";
		String y = "easy";
		String z = x.concat(y);
		
		z = z.replace("easy", "hard");
		
		System.out.println(z);
		
		if(z.equals("Studyeasy")){
			System.out.println("Text is Studyeasy");
		}else{
			System.out.println("Text is not Studyeasy");
		}
	}

}

```

Strings might have inconsistentency when used with concationation or  == methods or operator.
```java

string x = "Study";
string y = "easy";
string z = x + y;

if(z == "Studyeasy"){
    System.out.println("Text is Studyeasy");
}else{
    System.out.println("Text is not Studyeasy");
}

```
but the output will be "Text is not Studyeasy" because the == method compares the memory location of the string and not the value of the string.
so instead what we can use is z.equals("Studyeasy").  java has methods for all the data types to compare the values of the data types like equals() for strings, equalsIgnoreCase() for strings, compareTo() for strings, 
concat(). so use concat() instead of + operator for strings.  

### Difference between string literals and string objects

Let say we have str1 and str2 variables of type string.  
```java
    String str1 = "Hello world !!";
    String str2 = "Hello world !!";
```

for the str1 it would be stored in a heap with some memory address and in a memory stack it will have the reference for the variable str1 with 
the memory address of the heap. now if str2 has the same data then java won't create a new memory in the heap instead it will point to the same memory address of the str1. so str1 and str2 will be pointing to the same memory address in the heap.
and reference for str2 will be stored in the memory stack. so str1 and str2 will be pointing to the same memory address in the heap.
if data was different then java would have created a new memory in the heap and stored the new reference in the memory stack.
str1 == str2 will return true because both are pointing to the same memory address in the heap.

Now let say we have str3 and str4 variables of type string.  
```java
    String str3 = new String("Hello world !!");
    String str4 = new String("Hello world !!");
```
Here since we are using new keyword to create a new object in the heap so java will create a new memory in the heap and store the data and the new reference for the variable str3 in the memory stack. and for str4 it will create a new memory in the heap and store the data and the reference for the variable str4 in the memory stack. 
so str3 and str4 will be pointing to the different memory address in the heap and also in the memory stack. so str3 == str4 will return false because both are pointing to the different memory address in the heap.
but if we use str3.equals(str4) then it will return true because it will compare the values of the string and not the memory address.

### vvimp: When to use what ? object ? literal ?
Use String literals usually it is a recommended way.
(It enable compiler optimization and saves memory because no new objects are created if it exists already in the string pool.)
Eg: String str = "Hello world !!";
Use .equals() method for string comparison always.

