
### Why we need oop in first place ?

OOP or object oriented programming makes your code more  organised, modular, and reusable.

### what are classes ?
 classes are named group of properties and functionalities on top of which objects are to be built.

for example:

```
class car{
int engine
int seatCapacity
int modelName
}
```

so this a class of car or template of a car so for every car anyone builds they must have a engine capacity , seat capacity lets  and a ModelName

like this 

```
// Creating an object of the Car class 

Car myCar = new Car(); // Setting values for the attributes of the object 
myCar.engine = 2000; 
myCar.seatCapacity = 5;
myCar.modelName = "Toyota Camry";
```

But whats the difference of between a class and an object ??

### class vs  object

Objects are instances of the class; they take up memory space to exist. Classes, on the other hand, are just templates, and they don't have a physical instance in most cases.



### working with objects 

when we delcare a class like this ;
```
class car{
int engine
int seatCapacity
int modelName
}
```

we create a class, now to declare a object using it we can do something like this 

```
car maruti-800;
```

but this wont create a object rather just (initialise the object or )create a memory space for the object in the stack memory (not heap) and the reference variable that is ```maruti-800```here will not point anywhere right now , However to declare a object we have to use ``new()`` constructor like this 

```
// Creating an object of the Car class 

Car myCar = new Car(); // new() will allocate memory in heap at runtime
myCar.engine = 2000; 
myCar.seatCapacity = 5;
myCar.modelName = "Toyota Camry";

```

now remember objects are stored in heap  memory while references are stored in stack memory .

![[Pasted image 20240317140152.png]]


alright now lets see about another case:

```
class student{
String name;
int roll;
float marks;
}
```

cool , here we created  a class of student now lets try to create a object with it 

```
student anshuman=new student();
anshuman.name="Anshuman";
anshuman.roll=4;
anshuman.marks=7.5;
```

cool now lets try to print it

```
public class Student {
    String name;
    int roll;
    float marks;

    public static void main(String[] args) {
        // Creating an object of the Student class
        Student anshuman = new Student();

        // Setting values for the attributes of the object
        anshuman.name = "Anshuman";
        anshuman.roll = 4;
        anshuman.marks = 7.5;

        // Printing the details of the object
        System.out.println("Name: " + anshuman.name);
        System.out.println("Roll: " + anshuman.roll);
        System.out.println("Marks: " + anshuman.marks);
    }
}

```

as predicted the output will be like this only

```
Name: Anshuman
Roll: 4
Marks: 7.5

```

however what if we do something like this :

```
public class Student {
    String name;
    int roll;
    float marks;

    public static void main(String[] args) {
        // Creating an object of the Student class
        Student anshuman = new Student();

        // Printing the details of the object
        System.out.println("Name: " + anshuman.name);
        System.out.println("Roll: " + anshuman.roll);
        System.out.println("Marks: " + anshuman.marks);
    }
}
```

so in this case output will be like this ;

```
Name: null
Roll: 0
Marks: 0.0

```

but why so ?thats because when to try to print it the program will look for object.value but if it doesn't find it it will go with the default value only and the default value for `primitive` data types is `0` but for objects / complex data types like String its ``null``.

However till now we had to print each value of the object one by one and also assign values one by one , how to do it dynamically ? that's where ` Student anshuman = new Student();` the constructor function comes in this case its `student()`  -> [[Java Constructors]]]
