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
		
		return 64;
	}

}

## multiple inheritance using interface


