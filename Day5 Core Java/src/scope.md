#### scope
```java

package org.studyeasy;

public class App {
	

	public static void main(String[] args) {
		
		int i;
		for(i=1; i<10; i++){
			System.out.println(i);
		}
		System.out.println("**********");
		System.out.println(i);

	}

}

```
if there is an ambiguity priority will be given to the local variable that is declared inside the block or inner block.
ambiguity refers to when there is a variable with same name in both local and global scope.
to access global variable you need to specify access modifier as static. or if public access it using making an object of the class.variable name.
we have to specify static a variable only if it is outside static main method. if inside main method no need to specify static.
you can use int i = 10;


