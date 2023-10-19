## Interfaces

it helps us to standarized our application so that we can apply rules and regulations on our application and classes.
Interface can be used to achieve polymorphism in java.
it has override witten in class above some functions that means that these functions are overriden by the interface.
access specifier are not required in interface as they are by default public.

package org.studyeasy;

import org.studyeasy.phone.OnePlus5;
import org.studyeasy.phone.Phone;

public class Hello {

	public static void main(String[] args) {
		Phone phone = new OnePlus5();
		
		System.out.println("Processor: "+phone.processor());
		System.out.println("Space in GB: "+phone.spaceInGB());
		
	}

}


package org.studyeasy.phone;

public class OnePlus5 implements Phone{

	@Override
	public String processor() {
		
		return "SD835";
	}

	@Override
	public String OS() {
		
		return "Android";
	}

	@Override
	public int spaceInGB() {
		
		return 64;
	}

}

package org.studyeasy.phone;

public interface Phone {
String processor();
String OS();
int spaceInGB();

}


package org.studyeasy.phone;

public class Iphone8 implements Phone{

	@Override
	public String processor() {
		
		return "A11";
	}

	@Override
	public String OS() {
		
		return "IOS";
	}

	@Override
	public int spaceInGB() {
		w
		return 64;
	}

}

## multiple inheritance using interface

# multiple inheritance using interface in concrete class will only work if the methods or signatures or return types 
# are not same in both the interfaces and concerte class has to implement all the methods of interfaces compulsory.

# while in abstract class it will work even if the methods or signatures but you have to explicitly tell one method from one interface as 
# abstract and implement the other. if both implemented then it will give error.


# override is written where the function is implemented in the class not where it is declared in the interface.
# similarly abstract class has the method eat() declared in it but it is implemented in the concrete class or child class 
# so in concrete or child class we have to override the method eat().
# similary in interface it is declared but implemented in person abstract class so we have to override it in person abstract class.

declaration no override
implementation @override


interface Interface1 {
void myMethod();
}

interface Interface2 {
void myMethod();
}

abstract class MyAbstractClass implements Interface1, Interface2 {
// Provide a concrete implementation for both methods (ambiguous)
public void myMethod() {
// Concrete implementation for one of the interfaces
}

    public void myMethod() {
        // Concrete implementation for the other interface (ambiguous)
    }

    public abstract void myMethodFromInterface2();
}


************************************************************

package org.studeasy;

import org.studeasy.person.NonVegan;
import org.studeasy.person.Person;
import org.studeasy.person.Vegan;

public class Hello {

	public static void main(String[] args) {
		Person john = new Vegan();
		john.breathe();
		john.eat();
		john.speak();
		john.message();
		

	}

}

package org.studeasy.person;

public interface IsAlive {
void breathe();

}

package org.studeasy.person;

public interface LiveLife {
void message();
}

package org.studeasy.person;

public class NonVegan extends Person{

	@Override
	public void eat() {
		System.out.println("Eats non vegan food");
		
	}

}


package org.studeasy.person;

public abstract class Person implements IsAlive,LiveLife{

	public void speak(){
		System.out.println("Shares his/her thoughts.");
	}
	
	@Override
	public void breathe(){
		System.out.println("be alive; remain living.");
	}
	
	@Override
	public void message(){
		System.out.println("life is journey, keep moving and meet new people.");
	}
	public abstract void eat();

}


package org.studeasy.person;

public class Vegan extends Person{

	@Override
	public void eat() {
		System.out.println("Eats vegan food");
		
	}

}


