# Inheritance
inheritance means that one class can inherit the attributes and methods of another class.

Bike car and Truck.
BIke has wheels , engine, seats, handle, fuel tank, lights
Car has wheels, engine, seats, steering wheel, fuel tank, lights
Truck has wheels, engine, seats, steering wheel, fuel tank, lights, trailer

A lot of them has common attributes and methods. So we can create a class called Vehicle and make all of them inherit from it.
common properties are wheels, engine, seats, fuel tank, lights.

properties of parent class are inherited by child class.
![img.png](img.png)

package org.studyeasy;

import org.studyeasy.vehicles.Bike;

public class Demo {

	public static void main(String[] args) {
		Bike bike = new Bike();
		bike.handle = "Short";
		bike.engine = "Petrol";
		
		System.out.println(bike.engine);

	}

}
************************************************************
package org.studyeasy.parent;

public class Vehicle {

public String engine;
public int wheels;
public int seats;
public int fuelTank;
public String lights;
}

************************************************************

package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Bike extends Vehicle{
public String handle;

}

************************************************************
package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Car extends Vehicle{

	public String steering;
	public String musicSystem;
	public String airConditioner;
	public String fridge;
	public String entertainmentSystem;
}

************************************************************

package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Truck extends Vehicle{
public String	steering;
public String	musicSystem;
public String airConditioner;
public int	container;

}
***********************************************************

when a property is declared as private in parent class, it is no t inherited by child class.
we will get null pointer exception. field is not visible.
private property are not visible to child class. if their access specifier is private.

package org.studyeasy.parent;

public class Vehicle {

private String engine;
private int wheels;
private int seats;
private int fuelTank;
private String lights;

public Vehicle() {
this.engine = "petrol";
this.wheels = 4;
this.seats = 4;
this.fuelTank = 35;
this.lights = "LED";

}

	public Vehicle(String engine, int wheels, int seats, int fuelTank, String lights) {

		this.engine = engine;
		this.wheels = wheels;
		this.seats = seats;
		this.fuelTank = fuelTank;
		this.lights = lights;
	}

public String getEngine() {
return engine;
}

public int getWheels() {
return wheels;
}

public int getSeats() {
return seats;
}

public int getFuelTank() {
return fuelTank;
}

public String getLights() {
return lights;
}


}





package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Bike extends Vehicle{
private String handle;

	public Bike() {
		super();
		this.handle = "short";
	}

	public Bike(String handle) {
		super();
		this.handle = handle;
	}

	public String getHandle() {
		return handle;
	}


}



package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Car extends Vehicle{

	private String steering;
	private String musicSystem;
	private String airConditioner;
	private String fridge;
	private String entertainmentSystem;
	}



package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Truck extends Vehicle{
private String	steering;
private String	musicSystem;
private String airConditioner;
private int	container;


}



package org.studyeasy;

import org.studyeasy.vehicles.Bike;

public class Demo {

	public static void main(String[] args) {
		Bike bike = new Bike();
	    System.out.println(bike.getHandle());
	   System.out.println(bike.getEngine());
	}

}

# super() call to the default constructor of parent class.
we don't need to specify super() in parent class constructor.

here we are calling the default constructor of parent class and child class.

package org.studyeasy;

import org.studyeasy.vehicles.Bike;

public class Demo {

	public static void main(String[] args) {
        Bike bike = new Bike("long", "Deisel",4, 5, 40, "LED");
        System.out.println("Handle: "+bike.getHandle());
        System.out.println("Engine type: "+bike.getEngine());
        System.out.println("Number of seats: "+bike.getSeats());
        System.out.println("Feul tank capacity: "+bike.getFuelTank());
	    System.out.println("Head lamp type: "+bike.getLights());
	    System.out.println("Number of wheels: "+bike.getWheels());
	    
	
	}

}


package org.studyeasy.parent;

public class Vehicle {

private String engine;
private int wheels;
private int seats;
private int fuelTank;
private String lights;

public Vehicle() {
this.engine = "petrol";
this.wheels = 4;
this.seats = 4;
this.fuelTank = 35;
this.lights = "LED";

}

	public Vehicle(String engine, int wheels, int seats, int fuelTank, String lights) {

		this.engine = engine;
		this.wheels = wheels;
		this.seats = seats;
		this.fuelTank = fuelTank;
		this.lights = lights;
	}

public String getEngine() {
return engine;
}

public int getWheels() {
return wheels;
}

public int getSeats() {
return seats;
}

public int getFuelTank() {
return fuelTank;
}

public String getLights() {
return lights;
}


}


package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Bike extends Vehicle{
private String handle;

	public Bike() {
		super();
		this.handle = "short";
	}

	public Bike(String handle,String engine, int wheels, int seats, int fuelTank, String lights) {
		super(engine,wheels,seats,fuelTank,lights);
		this.handle = handle;
	}

	public String getHandle() {
		return handle;
	}


}

package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Car extends Vehicle{

	private String steering;
	private String musicSystem;
	private String airConditioner;
	private String fridge;
	public String entertainmentSystem;
	}

package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Truck extends Vehicle{
private String	steering;
private String	musicSystem;
private String airConditioner;
private int	container;

}

# parameterized constructor of parent class.

How to call the parameterized constructor of parent class from child class.

package org.studyeasy;

import org.studyeasy.vehicles.Bike;

public class Demo {

	public static void main(String[] args) {
        Bike bike = new Bike("long", "Deisel",4, 5, 40, "LED");
        System.out.println("Handle: "+bike.getHandle());
        System.out.println("Engine type: "+bike.getEngine());
        System.out.println("Number of seats: "+bike.getSeats());
        System.out.println("Feul tank capacity: "+bike.getFuelTank());
	    System.out.println("Head lamp type: "+bike.getLights());
	    System.out.println("Number of wheels: "+bike.getWheels());
	    
	
	}

}
package org.studyeasy.parent;

public class Vehicle {

private String engine;
private int wheels;
private int seats;
private int fuelTank;
private String lights;

public Vehicle() {
this.engine = "petrol";
this.wheels = 4;
this.seats = 4;
this.fuelTank = 35;
this.lights = "LED";

}

	public Vehicle(String engine, int wheels, int seats, int fuelTank, String lights) {

		this.engine = engine;
		this.wheels = wheels;
		this.seats = seats;
		this.fuelTank = fuelTank;
		this.lights = lights;
	}

public String getEngine() {
return engine;
}

public int getWheels() {
return wheels;
}

public int getSeats() {
return seats;
}

public int getFuelTank() {
return fuelTank;
}

public String getLights() {
return lights;
}


}
package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Bike extends Vehicle{
private String handle;

	public Bike() {
		super();
		this.handle = "short";
	}

	public Bike(String handle,String engine, int wheels, int seats, int fuelTank, String lights) {
		super(engine,wheels,seats,fuelTank,lights);
		this.handle = handle;
	}

	public String getHandle() {
		return handle;
	}


}
package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Car extends Vehicle{

	private String steering;
	private String musicSystem;
	private String airConditioner;
	private String fridge;
	public String entertainmentSystem;
	}

package org.studyeasy.vehicles;

import org.studyeasy.parent.Vehicle;

public class Truck extends Vehicle{
private String	steering;
private String	musicSystem;
private String airConditioner;
private int	container;

}

when a object is printed it directly calls the toString() method of the object class. but we can override it.
![img_1.png](img_1.png)
highlight the file then right click and select source and generate toString() method.
select values from the methods and inherit methods. make sure to not select getClass() hascode and toString() methods.

# to see how constructors getter setters inheritance and toString() super() works see section 8 working with inheritance challenge folder 
all files of vehicle, demo, bike, car, truck are there.

# Overriding methods in inheritance

let's say you write a method in parent class

public void run() {
System.out.println("Vehicle is running");
}
 and same method in child class lets say bike to have the exact same method.
# then when you call the method from child class object it will call the method from child class and not from parent class. by calling bike.run();
if run method is only in parent class then it will call the method from parent class.

# Type of inheritance and exercise information.
1. Single inheritance: when a class inherits from only one class. where parent is known as parent class and child is known as child class or subclass.
2. Multiple inheritance: when a class inherits from more than one class. multiple inheritance is not allowed in java. because of ambiguity. parent classes may have same methods names and properties. so it is not allowed in java. you may get run time error.
3. Hierarchical inheritance: when one parent class is inherited by multiple child classes.
4. Multi-level inheritance: when a class inherits from a class which is already a child class of another class. in java parent class are known as super class and child clasas are known as subclass.
5. Hybrid inheritance: when a class is inherited from multiple classes and one of the parent class is inherited by another class. it is not allowed in java.
![img_2.png](img_2.png) might give error same reason as multiple inheritance.
if methods are not same then it will work.


Exercise:
class animal: parent class
properties: height, weight, animalType, bloodType

class reptile: child class
properties: Dry skin, backbone, soft-shelled eggs

class Fish : child class
properties: live in water, has gills

class Birds: child class
properties: Animals with feathers, can fly

class Crocodile: child class of reptile
properties: hard-shelled eggs, shovInfo() will give all the information about the crocodile.
override  soft-shelled eggs to hard-shelled eggs.

class Eel: child class of fish
properties: release electric charge, shovInfo() will give all the information about the Eel.

class Eagle: child class of birds
properties: shovInfo() will give all the information about the Eagle.

add shovent() method in all the classes.

see test-inheritance folder for all the files. for solution. # Default values exercise t

Protected is used when we want to access the properties of parent class in child class. but we don't want to access it outside the package.
private when you don't need to access it outside the class.

To string is a method through which we can print the object of a class. it is a method of object class. we can override it.
we can print the values of the properties of the object.

# Composition
Composition is used where inheritance is not possible.
where multiple components work together to create a single entity is called composition.
For example:
Laptop computer and mobile phone.
components of laptop are keyboard, mouse, screen, motherboard, processor, ram, hard disk, battery, charger.
These components are simple in few cases and complex in few cases.
list of components:
Simple components:
screen -> Full HD/HD
Ram -> 4GB/8GB/16GB
Hard disk -> 1TB/2TB

Complex components:
Graphics card -> Complex component
optical drive -> single layer/dual layer
keyboard -> mechanical/membrane

Processor:
Brand
Generation
Cores
Clock speed
series
cache memory

Graphics card:
Brand
Memory
series

# So for a Composition of Laptop
class: Laptop
screen -> Property
Ram -> Property
Hard disk -> Property
Graphics card -> Class
optical drive -> Property
keyboard -> Property
Processor -> Class

properties can be same for parent and class in composition but in inheritance it is not possible.

package org.studyeasy;

import org.studyeasy.laptop.Laptop;

public class Hello {

	public static void main(String[] args) {
		Laptop lappy = new Laptop();
		System.out.println(lappy);

	}

}

package org.studyeasy.laptop;

import org.studyeasy.laptop.components.GraphicsCard;
import org.studyeasy.laptop.components.Processor;

public class Laptop {

	private float screen;
	private Processor processor;
	private String ram;
	private String hardDrive;
	private GraphicsCard graphicsCard;
	private String opticalDrive;
	private String keyboard;

	public Laptop() {

		this.screen = 15.6f;
		this.processor = new Processor();
		this.ram = "DDR4";
		this.hardDrive = "2TB";
		this.graphicsCard = new GraphicsCard();
		this.opticalDrive = "MLT layer";
		this.keyboard = "backlit";
	}

	public Laptop(float screen, Processor processor, String ram, String hardDrive, GraphicsCard graphicsCard,
			String opticalDrive, String keyboard) {
		super();
		this.screen = screen;
		this.processor = processor;
		this.ram = ram;
		this.hardDrive = hardDrive;
		this.graphicsCard = graphicsCard;
		this.opticalDrive = opticalDrive;
		this.keyboard = keyboard;
	}

	@Override
	public String toString() {
		return "Laptop [screen=" + screen + ", processor=" + processor + ", ram=" + ram + ", hardDrive=" + hardDrive
				+ ", graphicsCard=" + graphicsCard + ", opticalDrive=" + opticalDrive + ", keyboard=" + keyboard + "]";
	}

}

package org.studyeasy.laptop.components;

public class GraphicsCard {
private String brand;
private int series;
private String memory;

	public GraphicsCard() {
		this.brand = "Nvidia";
		this.series = 940;
		this.memory = "2 GB";
	}

	public GraphicsCard(String brand, int series, String memory) {

		this.brand = brand;
		this.series = series;
		this.memory = memory;
	}

	@Override
	public String toString() {
		return "GraphicsCard [brand=" + brand + ", series=" + series + ", memory=" + memory + "]";
	}

}

package org.studyeasy.laptop.components;

public class Processor {
private String brand;
private String series;
private int generation;
private int cores;
private int threads;
private String cacheMemory;
private String frequency;
private String minFrequency;
private String maxfrequency;

	public Processor() {
		this.brand = "intel";
		this.series = "i5 7200u";
		this.generation = 7;
		this.cores = 2;
		this.threads = 4;
		this.cacheMemory = "3MB";
		this.frequency = "2.5Ghz";
		this.minFrequency = "2.5Ghz";
		this.maxfrequency = "3.1Ghz";
		
	}

	public Processor(String brand, String series, int generation, int cores, int threads, String cacheMemory,
			String frequency, String minFrequency, String maxfrequency) {

		this.brand = brand;
		this.series = series;
		this.generation = generation;
		this.cores = cores;
		this.threads = threads;
		this.cacheMemory = cacheMemory;
		this.frequency = frequency;
		this.minFrequency = minFrequency;
		this.maxfrequency = maxfrequency;
	}

	@Override
	public String toString() {
		return "Processor [brand=" + brand + ", series=" + series + ", generation=" + generation + ", cores=" + cores
				+ ", threads=" + threads + ", cacheMemory=" + cacheMemory + ", frequency=" + frequency
				+ ", minFrequency=" + minFrequency + ", maxfrequency=" + maxfrequency + "]";
	}

}

# compostion is used more than inheritance in real world.

# Working with composition 

in composition you use object inside object to call the properties and methods of the object.
package org.studyeasy;

import org.studyeasy.laptop.Laptop;

public class Hello {

	public static void main(String[] args) {
		Laptop lappy = new Laptop();
		System.out.println(lappy.getProcessor().getBrand());

	}

}


package org.studyeasy.laptop;

import org.studyeasy.laptop.components.GraphicsCard;
import org.studyeasy.laptop.components.Processor;

public class Laptop {

	private float screen;
	private Processor processor;
	private String ram;
	private String hardDrive;
	private GraphicsCard graphicsCard;
	private String opticalDrive;
	private String keyboard;

	public Laptop() {

		this.screen = 15.6f;
		this.processor = new Processor();
		this.ram = "DDR4";
		this.hardDrive = "2TB";
		this.graphicsCard = new GraphicsCard();
		this.opticalDrive = "MLT layer";
		this.keyboard = "backlit";
	}

	public Laptop(float screen, Processor processor, String ram, String hardDrive, GraphicsCard graphicsCard,
			String opticalDrive, String keyboard) {
		this.screen = screen;
		this.processor = processor;
		this.ram = ram;
		this.hardDrive = hardDrive;
		this.graphicsCard = graphicsCard;
		this.opticalDrive = opticalDrive;
		this.keyboard = keyboard;
	}

	@Override
	public String toString() {
		return "Laptop [screen=" + screen + ", processor=" + processor + ", ram=" + ram + ", hardDrive=" + hardDrive
				+ ", graphicsCard=" + graphicsCard + ", opticalDrive=" + opticalDrive + ", keyboard=" + keyboard + "]";
	}

	public Processor getProcessor() {
		return processor;
	}

	public float getScreen() {
		return screen;
	}

	public String getRam() {
		return ram;
	}

	public String getHardDrive() {
		return hardDrive;
	}

	public GraphicsCard getGraphicsCard() {
		return graphicsCard;
	}

	public String getOpticalDrive() {
		return opticalDrive;
	}

	public String getKeyboard() {
		return keyboard;
	}


}


package org.studyeasy.laptop.components;

public class GraphicsCard {
private String brand;
private int series;
private String memory;

	public GraphicsCard() {
		this.brand = "Nvidia";
		this.series = 940;
		this.memory = "2 GB";
	}

	public GraphicsCard(String brand, int series, String memory) {

		this.brand = brand;
		this.series = series;
		this.memory = memory;
	}

	@Override
	public String toString() {
		return "GraphicsCard [brand=" + brand + ", series=" + series + ", memory=" + memory + "]";
	}

}

package org.studyeasy.laptop.components;

public class Processor {
private String brand;
private String series;
private int generation;
private int cores;
private int threads;
private String cacheMemory;
private String frequency;
private String minFrequency;
private String maxfrequency;

	public Processor() {
		this.brand = "intel";
		this.series = "i5 7200u";
		this.generation = 7;
		this.cores = 2;
		this.threads = 4;
		this.cacheMemory = "3MB";
		this.frequency = "2.5Ghz";
		this.minFrequency = "2.5Ghz";
		this.maxfrequency = "3.1Ghz";
		
	}

	public Processor(String brand, String series, int generation, int cores, int threads, String cacheMemory,
			String frequency, String minFrequency, String maxfrequency) {

		this.brand = brand;
		this.series = series;
		this.generation = generation;
		this.cores = cores;
		this.threads = threads;
		this.cacheMemory = cacheMemory;
		this.frequency = frequency;
		this.minFrequency = minFrequency;
		this.maxfrequency = maxfrequency;
	}

	@Override
	public String toString() {
		return "Processor [brand=" + brand + ", series=" + series + ", generation=" + generation + ", cores=" + cores
				+ ", threads=" + threads + ", cacheMemory=" + cacheMemory + ", frequency=" + frequency
				+ ", minFrequency=" + minFrequency + ", maxfrequency=" + maxfrequency + "]";
	}

	public String getBrand() {
		return brand;
	}

	public String getSeries() {
		return series;
	}

	public int getGeneration() {
		return generation;
	}

	public int getCores() {
		return cores;
	}

	public int getThreads() {
		return threads;
	}

	public String getCacheMemory() {
		return cacheMemory;
	}

	public String getFrequency() {
		return frequency;
	}

	public String getMinFrequency() {
		return minFrequency;
	}

	public String getMaxfrequency() {
		return maxfrequency;
	}


}

# Adding functionality to the above program.

package org.studyeasy;

import org.studyeasy.laptop.Laptop;
import org.studyeasy.laptop.components.GraphicsCard;
import org.studyeasy.laptop.components.Processor;

public class Hello {

	public static void main(String[] args) {
		//Laptop lappy = new Laptop();		//System.out.println(lappy.getProcessor().getBrand());
		
		Processor processor = new Processor("intel", "7200U", 7, 4, 4, "6MB"
				+ "", "2.5Ghz", "2.5Ghz", "3.1Ghz");
		GraphicsCard graphicsCard = new GraphicsCard("Nvidia", 1050, "4GB");
		
		Laptop gamingLaptop = new Laptop(17f, processor,
				"DDR4", "2TB", graphicsCard, null, "backlit");
		
		System.out.println(gamingLaptop);
		gamingLaptop.gamingMode();
		System.out.println("Gaming mode on");
		System.out.println("Current frequency: "+gamingLaptop.getProcessor().getFrequency());

	}

}


package org.studyeasy.laptop;

import org.studyeasy.laptop.components.GraphicsCard;
import org.studyeasy.laptop.components.Processor;

public class Laptop {

	private float screen;
	private Processor processor;
	private String ram;
	private String hardDrive;
	private GraphicsCard graphicsCard;
	private String opticalDrive;
	private String keyboard;

	public Laptop() {

		this.screen = 15.6f;
		this.processor = new Processor();
		this.ram = "DDR4";
		this.hardDrive = "2TB";
		this.graphicsCard = new GraphicsCard();
		this.opticalDrive = "MLT layer";
		this.keyboard = "backlit";
	}

	public Laptop(float screen, Processor processor, String ram, String hardDrive, GraphicsCard graphicsCard,
			String opticalDrive, String keyboard) {
		this.screen = screen;
		this.processor = processor;
		this.ram = ram;
		this.hardDrive = hardDrive;
		this.graphicsCard = graphicsCard;
		this.opticalDrive = opticalDrive;
		this.keyboard = keyboard;
	}

	@Override
	public String toString() {
		return "Laptop [screen=" + screen + ", processor=" + processor + ", ram=" + ram + ", hardDrive=" + hardDrive
				+ ", graphicsCard=" + graphicsCard + ", opticalDrive=" + opticalDrive + ", keyboard=" + keyboard + "]";
	}

	public Processor getProcessor() {
		return processor;
	}

	public float getScreen() {
		return screen;
	}

	public String getRam() {
		return ram;
	}

	public String getHardDrive() {
		return hardDrive;
	}

	public GraphicsCard getGraphicsCard() {
		return graphicsCard;
	}

	public String getOpticalDrive() {
		return opticalDrive;
	}

	public String getKeyboard() {
		return keyboard;
	}
    public String gamingMode(){
    	processor.setFrequency(processor.getMaxfrequency());
    	return "Success";
    }

}

package org.studyeasy.laptop.components;

public class GraphicsCard {
private String brand;
private int series;
private String memory;

	public GraphicsCard() {
		this.brand = "Nvidia";
		this.series = 940;
		this.memory = "2 GB";
	}

	public GraphicsCard(String brand, int series, String memory) {

		this.brand = brand;
		this.series = series;
		this.memory = memory;
	}

	@Override
	public String toString() {
		return "GraphicsCard [brand=" + brand + ", series=" + series + ", memory=" + memory + "]";
	}

}


package org.studyeasy.laptop.components;

public class Processor {
private String brand;
private String series;
private int generation;
private int cores;
private int threads;
private String cacheMemory;
private String frequency;
private String minFrequency;
private String maxfrequency;

	public Processor() {
		this.brand = "intel";
		this.series = "i5 7200u";
		this.generation = 7;
		this.cores = 2;
		this.threads = 4;
		this.cacheMemory = "3MB";
		this.frequency = "2.5Ghz";
		this.minFrequency = "2.5Ghz";
		this.maxfrequency = "3.1Ghz";
		
	}

	public Processor(String brand, String series, int generation, int cores, int threads, String cacheMemory,
			String frequency, String minFrequency, String maxfrequency) {

		this.brand = brand;
		this.series = series;
		this.generation = generation;
		this.cores = cores;
		this.threads = threads;
		this.cacheMemory = cacheMemory;
		this.frequency = frequency;
		this.minFrequency = minFrequency;
		this.maxfrequency = maxfrequency;
	}

	@Override
	public String toString() {
		return "Processor [brand=" + brand + ", series=" + series + ", generation=" + generation + ", cores=" + cores
				+ ", threads=" + threads + ", cacheMemory=" + cacheMemory + ", frequency=" + frequency
				+ ", minFrequency=" + minFrequency + ", maxfrequency=" + maxfrequency + "]";
	}

	public String getBrand() {
		return brand;
	}

	public String getSeries() {
		return series;
	}

	public int getGeneration() {
		return generation;
	}

	public int getCores() {
		return cores;
	}

	public int getThreads() {
		return threads;
	}

	public String getCacheMemory() {
		return cacheMemory;
	}

	public String getFrequency() {
		return frequency;
	}

	public String getMinFrequency() {
		return minFrequency;
	}

	public String getMaxfrequency() {
		return maxfrequency;
	}

	public void setFrequency(String frequency) {
		this.frequency = frequency;
	}


}

# Encapsulation

Encapsulation is used to hide the data from outside world. it is also known as data hiding.
difference between hiding and encapsulation is that in encapsulation we provide the access to the data through methods.
in hiding we don't provide access to the data.
if access specifier is public then it by default provides setter without calling setter in the class or child class.
if private
if value for a property is not specified then and created a object then it will put value as null for string.
if setter method we can apply restrictions to the value of the property.

package org.studyeasy;

public class Hello {

	public static void main(String[] args) {
		Person john = new Person();
		System.out.println(john);
		Person pooja = new Person("Pooja",26,"Female");
		System.out.println(pooja);
		pooja.setAge(-30);
		System.out.println(pooja);

	}

}


package org.studyeasy;

public class Person {
private String name;
private int age;
private String gender;

	public Person() {
		this.name = "John Doe";
		this.age = 25;
		this.gender = "Male";
	}

	public Person(String name, int age, String gender) {

		this.name = name;
		this.age = age;
		this.gender = gender;
	}

	public boolean setAge(int age) {
		if(age >= 0 && age <= 100){
			this.age = age;
			return true;
		}
		return false;	
		
	}

	public String getName() {
		return name;
	}

	public int getAge() {
		return age;
	}

	public String getGender() {
		return gender;
	}

	@Override
	public String toString() {
		return "Person [name=" + name + ", age=" + age + ", gender=" + gender + "]";
	}
}

there is no compile time error but there is run time error.
so if not valid value is passed then it will not set the value and store default value.
if age is passed -30 it will not set age as -30 instead pput default value as 26. as previous since it returned false.

prefer to use parameterized constructor instead of default constructor. it will throw error if not valid value is passed.

# Polymorphism
Poly means many and morphism means forms.
it means multiple forms. It helps us to provide multiple forms for a object.
It is also known as late binding or dynamic binding or runtime binding.
polymorphism is closely related to inheritance.
polymorphism is a type of inheritance.

samsung not 8 is a phone.
Phone note8 = new SamsungNote8("Note 8");

note 8 will have two verison of features method. one from phone class and one from samsungnote8 class.
it will call the method from samsungnote8 class because it is the child class of phone class.
if not present in child class then it will call the method from parent class.

#### phone.java
package org.studyeasy.phone;

public class Phone {
private String model;

	public Phone(String model) {
		this.model = model;
	}
    
	public void features(){
		System.out.println("Feature phone");
	}

	public String getModel() {
		return model;
	}

}

### Nokia3310.java

package org.studyeasy.phone;

public class Nokia3310 extends Phone {

	public Nokia3310(String model) {
		super(model);
	}

}

### Hello.java

package org.studyeasy;
import org.studyeasy.phone.Nokia3310;
import org.studyeasy.phone.Phone;
import org.studyeasy.phone.SamsungNote8;

public class Hello {

	public static void main(String[] args) {
		
		Phone phone = new Phone("Nokia 3310");
		phone.features();
		System.out.println(phone.getModel());
		
		Phone note8 = new SamsungNote8("Note 8");
		System.out.println(note8.getModel());
		note8.features();
		
		Phone nokia3310 = new Nokia3310("Nokia 3310");
		System.out.println(nokia3310.getModel());
		nokia3310.features();
		
		
	}

}

### SamsungNote8.java

package org.studyeasy.phone;

public class SamsungNote8 extends Phone{

	public String model;

	public SamsungNote8(String model) {
		super(model);
	}
	
	public void features(){
		System.out.println("Andriod flagship");
	}

	public String getModel() {
		return model;
	}

}


# PolyMorphism part 2

A static method is a method that belongs to a class rather than an instance of a class. 
This means you can call a static method without creating an object of the class. Static methods are sometimes called class methods.

that means if ststic you can directly call main() for function main but if not static you need to create an object 
like below for calling phone, since class is Hello so new Hello().phone(1); for calling phone method.


package org.studyeasy;

import org.studyeasy.phone.Nokia;
import org.studyeasy.phone.Phone;
import org.studyeasy.phone.Samsung;

public class Hello {

	public static void main(String[] args) {
		
		
		Phone nokia3310 = new Hello().phone(1);
		System.out.println(nokia3310.getModel());
		nokia3310.features();
		
		
		
		Phone note8 =  new Hello().phone(2);
		System.out.println(note8.getModel());
		note8.features();
		
	
	
	}
	
	public Phone phone(int dailyDriver){
		switch(dailyDriver){
		case 1: return new Nokia("3310");
		case 2: return new Samsung("Note 5");
		}
		return null;
	}

}

package org.studyeasy.phone;

public class Phone {
private String model;

	public Phone(String model) {
		this.model = model;
	}
    
	public void features(){
		System.out.println("Feature phone");
	}

	public String getModel() {
		return model;
	}

}


package org.studyeasy.phone;

public class Nokia extends Phone {

	public Nokia(String model) {
		super(model);
	}

}


package org.studyeasy.phone;

public class Samsung extends Phone{

	public Samsung(String model) {
		super(model);
	}
	
	public void features(){
		System.out.println("Andriod flagship");
	}

}


## Benefits of polymorphism

smart switching is also called as dynamic binding or late binding or runtime binding.





 






































