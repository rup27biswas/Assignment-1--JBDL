# Assignment-1--JBDL

**********************************Q1.What is the interface?**********************************

Answer:

An interface in Java is a blueprint of a class. It has static constants and abstract methods.

The interface in Java is a mechanism to achieve abstraction. There can be only abstract methods in the Java interface, not method body. It is used to achieve abstraction and multiple inheritance in Java.

In other words, you can say that interfaces can have abstract methods and static final variables. It cannot have a method body.All the methods and variables are implicitly public.

java 8 ==>

Since Java 8, we can have default and static methods in an interface.Any interface with a SAM(Single Abstract Method) is a functional interface, and its implementation may be treated as lambda expressions.It's recommended that all functional interfaces have an informative @FunctionalInterface annotation.

interface MyInterface{  
    /* This is a default method so we need not to implement this method in the implementation classes  */
    default void newMethod(){  
        System.out.println("Newly added default method");  
    }  
    
    /* This is a static method. Static method in interface is similar to default method except that we cannot override them in the implementation classes. Similar to default methods, we need to implement these methods in implementation classes so we can safely add them to the existing interfaces.*/
	
    static void anotherNewMethod(){
    	System.out.println("Newly added static method");
    }
    /* Already existing public and abstract method We must need to implement this method in  implementation classes.*/
    void existingMethod(String str);  
}  
public class Example implements MyInterface{ 
	// implementing abstract method
    public void existingMethod(String str){           
        System.out.println("String is: "+str);  
    }  
    public static void main(String[] args) {  
    	Example obj = new Example();
    	
    	//calling the default method of interface
        obj.newMethod();     
        //calling the static method of interface
        MyInterface.anotherNewMethod();
        //calling the abstract method of interface
        obj.existingMethod("Java 8 is easy to learn"); 
        
  
    }  
}

***************************Q2.What is an abstract class?**********************************

Answer:
A class which is declared as abstract is known as an abstract class. It can have abstract and non-abstract methods. It needs to be extended and its abstract method need to be implemented. It cannot be instantiated.

Points to Remember
An abstract class must be declared with an abstract keyword.
It can have abstract and non-abstract methods.
It cannot be instantiated.
It can have constructors and static methods also.
It can have final methods which will force the subclass not to change the body of the method.

**********************************Q3.Difference between throw and throws?**********************************

Answer:

Java throw keyword is used to throw an exception explicitly in the code, inside the function or the block of code.
Java throws keyword is used in the method signature to declare an exception which might be thrown by the function while the execution of the code.

Type of exception Using throw keyword, we can only propagate unchecked exception i.e., the checked exception cannot be propagated using throw only.
Using throws keyword, we can declare both checked and unchecked exceptions. However, the throws keyword can be used to propagate checked exceptions only.

The throw keyword is followed by an instance of Exception to be thrown.
The throws keyword is followed by class names of Exceptions to be thrown.

throw is used within the method.
throws is used with the method signature.

We are allowed to throw only one exception at a time i.e. we cannot throw multiple exceptions.
We can declare multiple exceptions using throws keyword that can be thrown by the method. For example, main() throws IOException, SQLException.

public class TestThrowAndThrows  
{  
    // defining a user-defined method  
    // which throws ArithmeticException  
    static void method() throws ArithmeticException  
    {  
        System.out.println("Inside the method()");  
        throw new ArithmeticException("throwing ArithmeticException");  
    }  
    //main method  
    public static void main(String args[])  
    {  
        try  
        {  
            method();  
        }  
        catch(ArithmeticException e)  
        {  
            System.out.println("caught in main() method");  
        }  
    }  
}

**********************************Q4.What is abstraction, encapsulation, polymorphism?**********************************

**Encapsulation:

Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as data hiding.

To achieve encapsulation in Java −
Declare the variables of a class as private.
Provide public setter and getter methods to modify and view the variables values.

**Abstraction:

As per dictionary, abstraction is the quality of dealing with ideas rather than events. For example, when you consider the case of e-mail, complex details such as what happens as soon as you send an e-mail, the protocol your e-mail server uses are hidden from the user. Therefore, to send an e-mail you just need to type the content, mention the address of the receiver, and click send.

Likewise in Object-oriented programming, abstraction is a process of hiding the implementation details from the user, only the functionality will be provided to the user. In other words, the user will have the information on what the object does instead of how it does it.

In Java, abstraction is achieved using Abstract classes and interfaces.

**Polymorphism

The dictionary definition of polymorphism refers to a principle in biology in which an organism or species can have many different forms or stages. This principle can also be applied to object-oriented programming and languages like the Java language. Subclasses of a class can define their own unique behaviors and yet share some of the same functionality of the parent class.

**********************************Q5.What is inheritance and its types?**********************************

Inheritance is the process of creating a new Class, called the Derived Class , from the existing class, called the Base Class . The Inheritance has many advantages, the most important of them being the reusability of code. Rather than developing new Objects from scratch, new code can be based on the work of other developers, adding only the new features that are needed. The reuse of existing classes saves time and effort.

However, inheritance may be implemented in different combinations in Object-Oriented Programming languages as below:

Single Inheritance
Multi Level Inheritance
Hierarchical Inheritance
Hybrid Inheritance
Multipath inheritance
Multiple Inheritance

**********************************Q6.What is the final,finalize,finally keyword?**********************************

**final**
            Definition : Final is a keyword and access modifier, which is used to put restrictions on class, methods and variables.
            Applicable to : Final keyword is used with classes, methods, and variables.
            Functionality : 1) Once declared, final variable become constant and can not be modified.
                            2) final method can not be overidden by subclass.
                            3) final class can not be inherited.
            Execution : Final method is executed only when we call it.

**finally**
            Definition : finally is a block in java exception handling to execute the important piece of code whether
                        the exception occurs or not.
            Applicable to: finally block is always related to try and catch block in exception handling.
            Functionality: 1)finally block runs the important code whether exception occured or not.
                           2)finally block free up all the resources used in try block.
            Execution : 1) Finally block is executed as soon as the try catch blocks are executed.
                        2) it's execution is not dependent on the exception.
          
**finalize**
            Definition : finalize() is the method in java which is used to perform cleanup processing, just before the object is garbage collected.
            Applicable to: finalize() method is used with objects.
            Functionality : finalize() method perfoms the cleanup activity with respect to the object, before its destructions.
            Execution : finalize() method is executed just before the object is destroyed.
            
**********************************Q7.What is a collection?**********************************

 The Collection in java is a framework that provides an architecture to store and manipulate the group of objects.
            Java Collection can achieve all the operations that you perform on data such as searching, sorting, insertion, manipulation and deletion.
            Java Collection means a single unit of objects.
            Java Collection provides many interfaces (Set, List, Queue, Deque) and classes (ArrayList, LinkedList, PriorityQueue, HashSet, LinkedHashSet, TreeSet).

**********************************Q8.ArrayList vs LinkedList**********************************

ArrayList and LinkedList both implements List Interface and maintains insertion order. Both are non synchronised classes.
            Differences between ArrayList and LinkedList :
            **ArrayList**
            1)ArrayList internally uses dynamic array to store the elements.
            2)Manipulations with ArrayList are slow, as it internally uses array. If any element is removed from the array, then all the bits are shifted in memory.
            3)An ArrayList class can act as list only because it implements List interface.
            4)ArrayList is better for storing and accessing data.
            **LinkedList**
            1)Linked List internally uses doubly linked list to store the elements.
            2)Manipulations in LinkedList are faster than ArrayList because it uses doubly linked list internally, so no bit shifting is required in memory.
            3)LinkedList class can act as a List and Queue both because it implements both List and Deque interfaces.
            4)LinkedList is better for manipulating data.
            
 **********************************Q9.equal vs == difference**********************************
 
 1) main difference is that equal() is method and == is an operator.
 2) We use == operattor for reference comparision(address comparision) and equal() method for content comparision.










