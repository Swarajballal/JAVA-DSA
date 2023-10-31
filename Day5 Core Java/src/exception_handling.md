## exception handling

package org.studyeasy;
```java


public class App {

	public static void main(String[] args) {
        App obj = new App();
        obj.case2(10, 0);
	}

	public void case1(int x, int y) {
		if (y != 0) {
			System.out.println(x / y);
		}else{
			System.out.println("The value of y is 0");
		}
	}

	public void case2(int x, int y) {
		try{
		  System.out.println(x / y);
		}catch(Exception e){
			System.out.println("The value of y is 0");
		}
	} 

}

```

```java

package org.studyeasy;

public class App {

	public static void main(String[] args) {
		int x = 0;
		try{
		
		    System.out.println("We don't know, what will be the outcome "+x/0);
		
		}catch (ArithmeticException e) {
			System.out.println("Arithmetic Exception occurred");
		}catch (Exception e) {
			System.out.println("Inside exception block");
		}
	}

}


```
subclass exception => superclass exception or main exception i.e (Exception e) => throwables => object 
heirarchy of exceptions : from left to right
these subclass may have their own subclass

There will not be a partial execution of a code for example

System.out.println("We don't know, what will be the outcome "+x/0);  // this will not be executed so this line will not be printed even if there 
is more parts to it they will not be executed

for example:

x = (10*10)/0;
part 1 is 10*10 and part 2 is 0 and part 3 is x = part1/part2 but then this will not be executed. 

### vvimp
exception case

int x = 0, y = 5;
try {
    System.out.println("We don't know, what will be the outcome "+y/x); x = (y = 10*10)/0;
} catch (Exception e) {
    System.out.println("Inside exception block");
}
System.out.println(y);

What will be the value of y ?
since partial execution is not possible so y value should not be updated and it should still be 5 but after running we see 
value of y = 100 which is contrary to what we thought. but (y = 10*10) is a complete statement and not partial statement 
so it will be executed and y will be updated to 100
y = 10*10 is a complete statement or a complete sub statement and not a partial statement so complete sub statement will be executed and 
partial statement will not be executed. concatination in previous example is a partial statement so it will not be executed.
System.out.println("We don't know, what will be the outcome "+x/0); 

when both sub exception and main exception are present then sub exception will be executed and main exception will not be executed 
because sub exception is more specific/accurate than main exception and java selects the most accurate exception to be executed.

you cant pur Exception e before ArithmeticException e because Exception e superclass and is capable of handling all the exceptions so artihmetic 
exception will never be executed hence error remember the heirarchy so sequence is important.
also runtime exception is superclass for arithmetic exception so if you put runtime exception before arithmetic exception then arithmetic exception
will never be executed.

so child exception should be put before parent exception.


### finally block

```java

package org.studyeasy;

public class App {

	public static void main(String[] args) {
		int x = 2;
		try{
		
		    System.out.println("We don't know, what will be the outcome "+x/2);
		
		}catch(RuntimeException e){
			System.out.println("Runtime exception");
			
		}catch(Exception e){
			System.out.println("Exception!!!");
		}
		finally{
			System.out.println("This will be get printed");
			System.out.println();
		}
	
	}

}

```

if we use finally then catch block is optional.
finally block will always be executed whether there is error or not irrespective of error finally block will get executed with exceptions if present.
#### vvimp 
if we use catch block let say they should always be before finally block because if we put catch block after finally block then it will give error
and also if multiple catch then they should be in sequence of child exception to parent exception.


Where to use finally block?
Where you want logic to be executed irrespective of error or not there you can use finally block.


### throws and throw

```java

package org.studyeasy;

import java.io.FileNotFoundException;

public class App {

	public static void main(String[] args) {
		try {
			someMethod();
		} catch (FileNotFoundException e) {
			System.out.println("catch block of main method");
		} catch (Exception e) {
			System.out.println("catch block of main method (Exception)");
		}
		
		
	}
	public static void someMethod() throws Exception{
		System.out.println("Message from someMethod");
		throw new Exception();
		
	}
}

```

Instead of using try catch block we can use throws keyword to throw the exception to the calling method and then the calling method can handle the exception.
you can throw a child exception or someMethod() throws Exception{} parent exception or someMethod() throws FileNotFoundException{} child exception.
so where the method is called from there you can handle the exception or you can throws from the place where the method is called so either handle try catch or throw but doing one of these is mandatory.
and it is mandatory to handle the exception in the place where method is called. you can throw exception outside the method.
but where the code is written you don't need to hence it is throws, throws at place where code is called.

When to make use of throw and throws ?
throws is to declare the exception and throw is to throw the exception.

void someMethod() throws FileNotFoundException{
    throw new FileNotFoundException();
    System.out.println("Message from someMethod");
}

here throws is used to throw the exception outside the method and throw is used to throw the exception from inside the method explicitly.
throw with object of exception class or object of any class which is child to exception class. specifically  the constructor of exception class or child
class of exception class. like FileNotFoundException() or Exception() or RuntimeException() or ArithmeticException() etc.

its like return statement once throw is executed then the next line will not be executed. you cannnot throws child class exception and throw a parent class this won't work.
you can throw a child exception and throws parent exception.


### user defined exception

```java

package org.studyeasy;

import java.io.FileNotFoundException;
class UserDefinedException extends Exception{
	
}

public class App {

	public static void main(String[] args) {
		try {
			someMethod();
		} catch (FileNotFoundException e) {
			System.out.println("catch block of main method(FileNotFoundException)"); 
		} catch (UserDefinedException e){
			e.printStackTrace();
		}catch (Exception e) {
			System.out.println("catch block of main method (Exception)");
		}

	}

	public static void someMethod() throws Exception,FileNotFoundException, UserDefinedException {
		int x = 3;

		switch (x) {
		case 1:
			throw new FileNotFoundException();
		
		case 2:
			throw new Exception();
			default:
				throw new UserDefinedException();
		}

	}
}

```


#### vvimp 
throwable is parent class of exception class and if you want to create a userdefined exception then you have to extend the class to exception class or throwable class.
since throwable is parent class of exception and you want to use throw new UserDefinedException(); then you have to extend userDefinedException class to throwable or exception class. 
since they are parent class of sub class exception.

subclass could be exsisting exception class or user defined exception class that we created.
throwable => exception => subclass exception (userDefinedException)
so you can extend by exception class
import UserDefinedException extends Exception then you can throw new UserDefinedException(); or you can extend by throwable class
import UserDefinedException extends Throwable then you can throw new UserDefinedException(); but you have to use throws keyword with userDefinedException in the method signature.
Exception class extended is unchecked exception and throwable class extended is checked exception. hence in throwable class you needed to mention the subclass exception in method signature and in 
Exception class you don't need to mention the subclass exception in method signature with throws.


### Checked and Unchecked Exceptions

```java

package org.studyeasy;

import java.io.FileNotFoundException;
import java.io.FileReader;

public class App {

	public static void main(String[] args) {
	
		try {
			FileReader in = new FileReader("file.txt");
		} catch (FileNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
		
	}	
}

```

ArithmeticException is unchecked exception and FileNotFoundException is checked exception.
so in ArithmeticException will give runtime error.

If we keep on checking minute exceptions then burden on system and performance will be affected hence we have unchecked exception.
Checked exceptions are those which are mandatory or bery important like files which needs to be checked and handled. like FileNotFoundException.













