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


