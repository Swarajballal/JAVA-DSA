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
