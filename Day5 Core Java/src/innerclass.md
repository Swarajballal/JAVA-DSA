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

#### static inner class

you can't mark outer class as static but you can mark inner class as static.
to access the methods as well as the property or method they have to be public.
also the way to access them is outerclassname.innerclassname.methodname();
and to access the property outerclassname.innerclassname.propertyname;

```java

package org.studyeasy.demo;

public class Outer {
	
	
	public static class Inner {
        public static int x = 0;
		public static void testingInnerMethod() {
			System.out.println("Testing inner class method.");
		}
	}

}

package org.studyeasy;

        import org.studyeasy.demo.Outer;

public class App {

   public static void main(String[] args) {
      Outer.Inner.testingInnerMethod();
      System.out.println(Outer.Inner.x);
   }

}

```

if you want to access a outer class variable from a static inner class then you need to create an object of 
outer class and then access the variable and then use it in the static inner class. but it is not a good way second way is if you make 
the outer property as static then you can access it directly from the static inner class so even if it is private variable then too it can access
the variable. that means inner class can access the private variable or method of outer class without creating an object.
how can we access the static inner class elements (methods, variables/properties) and properties from the outer class.
inner_class_name.variable_name;
inner_class_name.method_name();
if the method is static you can use it in diffrent class without making an object just by writing classname.methodname();
but if it is non-static method then you need to create an object of the class and then use it. new classname().methodname();
methods needs to be public to access them from outside the class.

```java
package org.studyeasy.demo;

public class Outer {
	
	public static void testOuterMethod(){
		System.out.println("Value of inner class variable: "+Inner.x);
		Inner.testingInnerMethod();
	}
	
	public static class Inner {
        public static int x = 0;
		public static void testingInnerMethod() {
			System.out.println("Testing inner class method.");
		}
	}

}

package org.studyeasy;

        import org.studyeasy.demo.Outer;

public class App {

   public static void main(String[] args) {
      Outer.testOuterMethod();
   }

}

```
#### Final keyword

we can assign final to a variable, method and class.
if you assign final to a variable you can't assign setter method to it. if you have already assigned a value to a variable then you can't
reassign it using a parameterized constructor, and let say you didn't declare the value of a final variable then the default constructor will 
complain and you wont't be able to use it.
when a vairable is marked final reassignment is not possible and if we have initialized the variable then we can't use default constructor 
and parameterized constructor.

```java
package org.studyeasy;

public class B extends A{
private final int x;


	public B(int x) {
		super();
		this.x = x;
	}

	public int getX() {
		return x;
	}

}

package org.studyeasy;

public class App {

	public static void main(String[] args) {
	
		B obj1 = new B(12);
		System.out.println(obj1.getX());
		
		
	}

}

package org.studyeasy;

public class A {

}
```

#### final keyword with class and method

you can't override a method if it has final indentifier.
if you want to apply final to all class instead of writing final in all class you can directly write class as final.
if you mark a class as final then you can't have subclass of that class or have a child class extends it properties if done using inheritance 
that means you have explictly write the method for child class since it won't be able to inherit parent class methods. since overriding is not
possible if marked final.
inheritance is not applicable for final classes so you have to remove final keyword from class.
```java

package org.studyeasy;

public final class A {
   public  void india(){
      System.out.println("India is amazing!");
   }

   public  void USA(){
      System.out.println("USA is fantastic");
   }

}

package org.studyeasy;

public class App {

   public static void main(String[] args) {

      B obj1 = new B();
      obj1.india();
      obj1.USA();

   }

}

package org.studyeasy;

public class B{
   private final int x =1;


   public int getX() {
      return x;
   }

   public void india() {
      System.out.println("Hello India, what's up?");
   }

   public  void USA(){
      System.out.println("USA is fantastic");
   }


}

```

#### Packages

```java

package org.studeasy.platform;

public class Java {
	public void usedFor(){
		System.out.println("Platform..");
	}

}

package org.studeasy.blog;

public class Java {
   public void userFor(){
      System.out.println("Blogging..");
   }

}

package org.studeasy;

        import org.studeasy.blog.Java;

public class App {

   public static void main(String[] args) {
      Java blog = new Java();
      blog.userFor();


   }

}

```
packages are a collection of src which has java files etc file.
now packages_name.  here package_name is the main package and . is to create sub related packages.
same name for multiple classes is not allowed in java so we use packages to differentiate between them. so we can have same name for classes
in different packages. wildcard '*' everything. directly you can't import and use them with class type and make an object. java will skip it and won't
give sugesstion for the method with same name in other class it will only show one.to get other you have to explicitly type package_name.related_package_name.class_name objectname = 
new package_name.related_package_name.class_name(); with this way we can remove the import statement.
see below example. 

```java

package org.studeasy;

import org.studeasy.blog.Java;


public class App {

   public static void main(String[] args) {
      Java blog = new Java();
      blog.userFor();

      org.studeasy.platform.Java platform = new org.studeasy.platform.Java();
      platform.usedFor();

   }

}

package org.studeasy.blog;

public class Java {
   public void userFor(){
      System.out.println("Blogging..");
   }

}

package org.studeasy.platform;

public class Java {
   public void usedFor(){
      System.out.println("Platform..");
   }

}

```

