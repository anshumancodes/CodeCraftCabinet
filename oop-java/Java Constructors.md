Constructors are nothing but special kind of functions that build instances of classes that is objects , like every time you want to create a instance of ```class student``` you build it with help of  `new student()` and as per the previous example to allocate the value to each property without using relational operator you can use the same constructor however you can to allocate values to each property as a norm. 

example:

```
class student {
int roll;
String Name;

public Student(int roll, String Name) { 
// Assigning values passed as arguments 
this.roll = roll; 
this.Name = Name; }

}


student Anshuman=new student(12,"Anshuman");

```

In the above example you can see the constructor is taking  arguments just like a function! but what the heck is `this` keyword used inside the public Student Constructor . so in Java, the `this` keyword is a reference to the current instance of the class , what it means is that this is a variable for your object lets say , here is what it looks like in  code example:

```
class Student {
    int roll;
    String Name;

    public Student(int roll, String Name) {
        // Assigning values passed as arguments
        this.roll = roll;
        this.Name = "Anshuman";
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating a new student object using the constructor
        Student Subham = new Student(12, "Subham");

        // Printing the name of the student
        System.out.println(Subham.Name);
    }
}

```

the output for the above code will be `Anshuman` for the `Subham` object because thats the Value provided in the Constructor but if i do something like this 

```

class Student {
    int roll;
    String Name;

    public Student(int roll, String Name) {
        // Assigning values passed as arguments
        this.roll = roll;
        this.Name = Name;
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating a new student object using the constructor
        Student Subham = new Student(12, "Subham");

        // Printing the name of the student
        System.out.println(Subham.Name);
    }
}
output :Subham


```

this will print `Subham ` as its output because the Constructor will take the value allocated for the `Subham` object and pass the value to the property of name , you can create a different student object and pass a different name too.

#### Constructor Overloading

Constructor Overloading Happens when we Have 2 or more Constructors defined with same name but with different properties like different no of parameters , access Control return type or whatever you wish to . lets see a example 


```

class Student {
    int roll;
    String Name;

    // Default constructor
    public Student() {
        
        this.Name ="Student Name";
        this.roll=0;
    }

    // Parameterized constructor
    public Student(int roll, String Name) {
        // Assigning values passed as arguments
        this.roll = roll;
        this.Name = Name;
    }
}

public class Main {
    public static void main(String[] args) {
        // Creating a new student object using the default constructor
        Student defaultStudent = new Student();
        System.out.println("Default Student Name: " + defaultStudent.Name);

        // Creating a new student object using the parameterized constructor
        Student parameterizedStudent = new Student(12, "Anshuman");
        System.out.println("Parameterized Student Name: " + parameterizedStudent.Name);
    }
}

```

output will be:

```
Default Student Name: Student Name
Parameterized Student Name: Anshuman
```



#### memory allocation or management for `new` keyword

well when we create or initialise a primitive data type like `int roll = 5`
we allocate certain memory space in the stack memory does the same thing happens with `new` well the answer is No because with  `new something()`   the reference variable will point to the object in heap memory and doesnt create any space in the stack memory ! but what if do something like this 


```
Student ashish=new Student()
Student Rahul=ashish;


```

will this copy `ashish` into `Rahul `and allocate some space well no! because `Rahul` just points to  `ashish ` object that already exists in the heap memory .

