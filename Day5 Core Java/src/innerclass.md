# innerclass
# most useful is non static inner class
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
