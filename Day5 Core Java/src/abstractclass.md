
## Abstract class

abstract class and interface goes hand in hand
interface provides complete abstraction, interfaces only have declaration of methods and no implementation.
implementation is done by the class that implements the interface.
when abstract is added before(prefix) class name then that class is called abstract class.
will have normal functions of class but also have abstract method.

## vvimp when the relationship is "Is A" relationship between two entities then we use abstract class if there is a requirement.
vegan is a person, a non veg is a person, a vegetarian is a person.

# Interfaces are used when there is a "Can" relationship between two entities. actions like singing, dancing, running, flying, swimming, etc.
# use interface like person can sing, person can dance, person can run, person can fly, person can swim, etc.

# When there is a multiple inheritance then we use interface. as multiple inheritance is not supported in java.

# vvimp the difference between abstract class and interface is that interface only has declaration of methods and no implementation.
# but abstract class can have both declaration and implementation of methods. or partial implementation of methods and partial declaration of methods.
# where you can call the declared function in other class later.

# interface used keyword is implements.
# abstract class used keyword is extends.

package org.studeasy;

import org.studeasy.person.NonVegan;
import org.studeasy.person.Person;
import org.studeasy.person.Vegan;

public class Hello {

	public static void main(String[] args) {
		Person john = new Vegan();
		john.speak();
		john.eat();
		System.out.println("************");
		Person mia = new NonVegan();
		mia.speak();
		mia.eat();
		

	}

}


package org.studeasy.person;

public class NonVegan extends Person{

	@Override
	public void eat() {
		System.out.println("Eats non vegan food");
		
	}

}

package org.studeasy.person;

public class Vegan extends Person{

	@Override
	public void eat() {
		System.out.println("Eats vegan food");

	}

}

package org.studeasy.person;

public abstract class Person {

	public void speak(){
		System.out.println("Shares his/her thoughts.");
	}
	
	public abstract void eat();

}
