### Enums

```java
package org.studyeasy;

public class Demo {
	public static void main(String[] args) {
		
		Learning learn = Learning.COREJAVA;
		
		switch(learn){
		case COLLECTIONS:
			System.out.println("Step 2 : Learning Collections framework");
			break;
		case COREJAVA:
			System.out.println("Step 1 : learning Core Java");
			break;
		case GENERICS:
			System.out.println("Step 3 : Learning Generics ");
			break;
		case JSPANDSERVLETS:
			System.out.println("Step 4 : Learning JSP and Servlets");
			break;
		case MUILTITHREADING:
			System.out.println("Step 5 : Learning MuiltThreading");
			break;
		default:
			System.out.println("Element not in the enumarated list");
			break;
		
		}
		
		for(Learning temp: Learning.values()){
			System.out.println(temp.ordinal());
		}
	}

}




package org.studyeasy;

public enum Learning {
	COREJAVA,COLLECTIONS,GENERICS,JSPANDSERVLETS,MUILTITHREADING
	
}
```

Enums is a collection of predefined constants , where constant is a variable whose value cannot be changed or final variable.
usually these variables are static and final.
Name of constants should be in uppercase letters.
passing the null value to switch case dosen't trigger the default case. so it should be enum.propertyname

