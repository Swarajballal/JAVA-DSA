# innerclass
# most useful is non-static inner class
inner class is a class inside a class
like a car class has a engine class inside it
we need to change the visibility of inner class to public if we want to access it outside the class


package org.studyeasy.shop;

public class Door {
private Lock lock;             // property of door class
public Door(){                 // constructor of door class
lock = new Lock(true);         // creating object of lock class and assigning default value true
}


	public Lock getLock() {     // getter method of lock class so that we can acess the lock class and set value of methods in lock class
		return lock;
	}


	public void shopStatus(){
		if(lock.isLock()){    // if lock is true then shop is closed
			System.out.println("Shop is closed, please visit later.");
		}else
		{
			System.out.println("Welcome, we are open.");
		}
	}

     public class Lock {
		private boolean lock;  // property of lock class

		public Lock(boolean lock) {    // constructor of lock class parameterized

			this.lock = lock;
		}

		public boolean isLock() {    // getter method of lock class
			return lock;
		}

		public void setLock(boolean lock) {  // setter method of lock class
			this.lock = lock;
		}

	}

}

package org.studyeasy;

import org.studyeasy.shop.Door;

public class Shop {

	public static void main(String[] args) {
		Door door = new Door();
		door.shopStatus();
		door.getLock().setLock(false);
		door.shopStatus();
	}

}



# Types of nested classes
1. Static nested class
2. Non-static nested class branch is also called as inner class branch. this is due to a instance of non-static inner class contains a instance of a
   inner class . like instance inside instance.

# non-static nested class has 3 types
1. Member inner/ inner class as shown above
2. Local inner class : which is inside a scope of a block which can be a block of code.
3. Anonymous inner class : no name class inside a class as there is no name it can only be used once in a lifetime.

# When it comes to static class no need to create object of outer class to access the static class. we don't need a object or instance we can directly access
# the static class.

# Local inner class


package org.studyeasy.shop;

public class Door {

	public boolean isLocked(String key) {

		class Lock {
			public boolean isLocked(String key) {
				if (key.equals("qwerty")) {
					return false;
				} else {
					return true;
				}
			}
		}
		return new Lock().isLocked(key);
	}

}

package org.studyeasy;

import org.studyeasy.shop.Door;

public class Shop {

	public static void main(String[] args) {
		Door door = new Door();
		if(door.isLocked(args[0])){
			System.out.println("Shop has closed, visit later");
		}else{
			System.out.println("Welcome, we are open :)");
		}
		System.out.println(args[1]);
		System.out.println(args[2]);


	}
}


# anonymous object

same above code but we don't need to create a object of lock class we can directly access it.
instead of this
Door door = new Door();
if(door.isLocked(args[0])){
System.out.println("Shop has closed, visit later");
}else{
System.out.println("Welcome, we are open :)");
}

it will be

if(new Door().isLocked(args[0])){
System.out.println("Shop has closed, visit later");
}else{
System.out.println("Welcome, we are open :)");
}

# anonymous inner class

what are anonymous inner class?
anonymous inner class is a class without a name. it is used to override a method of a class or interface.
anonynous methods are declared in abstract class but where ever they are called they are mandatory to override or implement the method.
anonynous objects don't need to imported as long as they are in the same package and can be created without a name.
package org.studyeasy;

import org.studyeasy.shop.Door;

public class Shop {

	public static void main(String[] args) {
		Door door = new Door();
		if(door.getLock().isUnlocked(args[0])){
			System.out.println("Welcome, we are open");
		}else{
			System.out.println("We are closed now, please visit later");
		}
	}

}


package org.studyeasy.shop;

public class Door{
private Lock lock = new Lock(){

		@Override
		public boolean isUnlocked(String keyCode) {
			if(keyCode.equals("qwerty")){
				return true;
			}else{
				return false;
			}
		}
		
	};
	public Lock getLock() {
		return lock;
	}

}

package org.studyeasy.shop;

public abstract class Lock{
public abstract boolean isUnlocked(String keyCode);
}

### Advantages of Inner Class 
1. Better real life depiction.
2. Inner class could be used only by outer class.
3. Easy access, as inner object is implicitly available inside outer object. 
Outer class acts as a normal class it can work with other class let say car class can communicate with signals traffic etc. 
Where engiene can be a inner class it has nothing to do with traffic class only , car class is communicating with signals and traffic 
class this is a real life example.

#### User Input :

```java
package org.studyeasy;

import java.util.Scanner;

public class App {

	public static void main(String[] args) {
		System.out.println("Whats your age?");
		Scanner sc = new Scanner(System.in); // alocates next line in terminal to take input
        int age = sc.nextInt(); // next line takes inputs from user and stores in age variable
        System.out.println("Your age is "+age);
        sc.close();
	}

}
```
sc.next() will wait for user input and then press enter and then it will print the output.
it also leads to resource leaks so use sc.close() to close the scanner class. you can also restrict the user
to enter only integer values by using sc.nextInt().

#### static keyword and elements

```java

package org.studyeasy;

import org.studyeasy.testrun.TestStatic;

public class App {

	public static void main(String[] args) {
	 
	   System.out.println("Current variable value: "+TestStatic.getStaticVariable());
	   TestStatic.setStaticVariable(1);
	   System.out.println("Current variable value: "+TestStatic.getStaticVariable());
	   TestStatic.setStaticVariable(24);
	   System.out.println("Current variable value: "+TestStatic.getStaticVariable());
	}

}

package org.studyeasy.testrun;

public class TestStatic {
   private static int staticVariable=0;

   public static int getStaticVariable() {
      return staticVariable;
   }

   public static void setStaticVariable(int staticVariable) {
      TestStatic.staticVariable = staticVariable;
   }


}

```
Default value of static variable is 0. static variable is shared by all the objects of the class.
so the next time we call the default value of static variable it will be 1. and then 24.
so normally new object will be created and the value will be 0 but in static variable it will be 1 and 24.
it updates the default value of static variable according to the last value of static variable.
static variable has an independent memory location. it has a single copy of variable in memory which is shared by all the objects of the class.
Static elements needs to be accessed by static methods only.
since it is a static method you don't need to create a object of the class to access the static variable or method.
but we cant make static class java doesn't allow it but there is a way to do it.
