# ASSIGNMENT-1 #

## **1.**  **Blocks :** ##
- **Define a class called Test.java**
- **Add main method.**
- **Write System.out.println statement inside method with some message.**
- **Define 2 static blocks with some statements inside it.**
- **Define 2 non-static blocks with some staements inside it.**
- **Create object of Test class inside main method using new. Run the Test class. See the output.**

 ### ***Program :*** ###
 ```java
 package org.assignment.block;

public class Test {
    static {
        System.out.println("Inside first static block."); // executed first
    }
    static {
        System.out.println("Inside second static block.");  // executed first
    }
    {
        System.out.println("Inside first non-static block.");  // executed third
    }
    {
        System.out.println("Inside second non-static block.");  // executed third
    }
    }
    public static void main(String[] args)
    {
        System.out.println("Inside main method");  // executed second
    }
        new Test(); 
    }
}
```
 ### ***Output :*** ###
      Inside first static block.
      Inside second static block.
      Inside main method
      Inside first non-static block.
      Inside second non-static block.
   
## **2.**  **Static Methods :** ##
- **Define a class called Test.java**
- **Define main method.**
- **Define 2 static methods called as m1() and m2() with both having void return type.
Add some statements in both of the methods.Call m1() from m2()**
- **From main method call m1() without creating object.**
- **Add a static block. call m1() from static block without using object. verify the output.**

 ### ***Program :*** ###
 ```java
 package org.assignment.activity2;

public class Test {
    static {
        System.out.println("static m1() call inside static block.");
        m1();
    }
    static void m1(){
        System.out.println("statement within static method m1()..");
    }
    static void m2(){
        System.out.println("statement within static method m2()..");
        m1();
    }
    public static void main(String[] args) {
        System.out.println("Inside main method..");
        m1();
    }
}
```
 ### ***Output :*** ###
    static m1() call inside static block.
    statement within static method m1()..
    Inside main method..
    statement within static method m1()..

## **3.**  **Non-Static Methods :** ##
- **Define a class called Test.java**
- **Define main method.**
- **Define 2 non-static methods called as m1() and m2() with both having void retunr type. Ass some statements in both of the methods.
call m1() from m2().****
- **Inside main method create object of Test using new. Test var = new Test().**
- **using above reference variable of Test call m1()**
- **Add a non static block. call m1() from non static block. verify the outout.**

 ### ***Program :*** ###
```java
package org.assignment.activity3;

public class Test {
    void m1(){
        System.out.println("statement within non-static method m1()...");
    }
    void m2(){
        System.out.println("statement within non-static method m2()...");
        m1();
    }
    {
        System.out.println("inside non-static block call method m1()..");
        m1();
    }
    public static void main(String[] args) {
        System.out.println("statement inside main()...");
        Test var = new Test();
        var.m1();
    }
}
```
 ### ***Output :*** ###
      statement inside main()...
      inside non-static block call method m1()..
      statement within non-static method m1()...
      statement within non-static method m1()...

 ## **4.**  **Parameterized Methods :** ##
- **Define a class called Test.java**
- **Define a main method.**
- **Create a static method sum(int x, int y) and having return type as int. This should give sum of x + y**
- **Call sum(10, 20) from main method and print the result inside main method**

 ### ***Program :*** ###
 ```java
 package org.assignment.activity4;

public class Test {
    static int sum(int x,int y){
        return x+y;
    }
    public static void main(String[] args) {
       int result= sum(10,20);
        System.out.println("Summation result of x and y is "+result);

    }
}
```
 ### ***Output :*** ###
    Summation result of x and y is 30

 ## **5.**  **Variable Declaration :** ##
- 
     * **You may see compilation error with this activity. Define a class called Test.java**
     * **Define a main method.**
     * **Declare a static variable x of type int at the class level. Declare a non static varaible y of type String at
     the class level. Run the class. Verify output.**
     
- **Define a static block. print the value of x & y inside static block. Run the class. Verify output.**
- **Define a non-static block. print the value of x & y inside non-static block. Run the class. Verify output.**
- **Define a static method m1() with void return type. print the value of x & y inside static method. Run the class. Verify output.**
- **Define a non-static method m2() with void return type. print the value of x & y inside non-static method. Run the class. Verify output.**
- **print the value of x & y inside main method. Run the class. Verify output.****
- **Inside main method create object of Test class using new. Test var = new Test();**
- **call m2() using the reference variable var. Run the class. Verify output.**
- **Inside main method call m1() without object. Run the class. Verify output.**
- **What is the default value for x and y you are getting here?**

 ### ***Program :*** ###
 ```java
 package org.assignment.activity5;

public class Test {
    static int x;
    String y;

    static {
        System.out.println("In static block value of x is "+x);
//        System.out.println("In static block value of y is "+y); // compile time error
    }

    {
        System.out.println("Inside non-static block.."); // this non-static  block is executed at the time of object creation of this class.
        System.out.println("In non-static block value of x is "+x);
        System.out.println("In non-static block value of y is "+y); // before object creation the value of x and y are not printed.
    }
    public static void main(String[] args) {
        System.out.println("Inside main() value of x = "+x);
//       System.out.println("Inside main() value of y = "+y); // non-static variable y ,we can't access static method main()
        Test var = new Test(); // creating object of  class Test
        var.m2();
        m1();
    }

   public static void m1() // static method
   {
       System.out.println("In static method m1()  x ="+x);
//       System.out.println("In static method m1()  y = "+y); // compile time error ,we can't access non-static variable inside a static method m1().
   }
   public void m2() // non-static method
   {
       System.out.println("In non-static method m2() x = "+x);
       System.out.println("In non-static method m2()  y = "+y);

   }
}
 ```
  ### ***Output :*** ###
      
       In static block value of x is 0
       Inside main() value of x = 0
       Inside non-static block..
       In non-static block value of x is 0
       In non-static block value of y is null
       In non-static method m2() x = 0
       In non-static method m2()  y = null
       In static method m1()  x =0
       
       here,default value of x=0 and y= null.

 ## **6.**  **Variable Declaration & Intialization :** ##
 - **You may see compilation error with this activity. Define a class called Test.java**
- **Define a main method.**
- **Declare a static variable x of type int at the class level. Declare a non static varaible y of type String at the class level. Run the class. Verify output.**
- **Define a static block. Initialize x = 20; and print x. Run the class. Verify output.**
- **Define a static method m1(). Initialize x = 30; and print x. Run the class. Verify output.**
- **From the main method call m1() without object. Run the class. Verify output.**
- **Define a non static block. Initialize y = "hello"; and print y. Run the class. Verify output.**
- **Define a non static method m2(). Initialize y = "bye"; and print y. Run the class. Verify output.**
- **Inside main method create object of Test using new. Test var = new Test(); From the main method call var.m2(). Run the class. Verify output.**
 ### ***Program :*** ###
 ```java
 package org.assignment.activity6;

public class Test {
 static int x;
   String y;
   static {
       x = 20; // initialize static variable x
       System.out.println("In static block x =  "+ x);
   }

    {
        y = "hello"; //  initialize non-static variable y
        System.out.println("In non-static block y =  "+ y);

    }

   static void m1() // static method
   {
       x = 30;
       System.out.println("In static m1() x =  "+ x);
   }

   void m2() // non-static method
   {
       y = "bye";
       System.out.println("In non-static m2() y = "+ y);
   }
    public static void main(String[] args) {
        m1();
        Test var = new Test();
        var.m2();
    }
}
 ```
 ### ***Output :*** ###
    Here,No compilation error occur
    
    In static block x =  20
    In static m1() x =  30
    In non-static block y =  hello
    In non-static m2() y = bye

 ## **7.**  **Final Variables or Constants :** ##
- **Define a class called Test.java**
- **Define a main method.**
- **Declare a final static variable x of int type. Try to initialize this 2 times.**
- **Declare a final non static variable y of int type. Try to initialize this 2 times.**
 
  ### ***Program :*** ###
  ```java
  package org.assignment.activity7;

public class Test {
    final static int x = 10;
    final static int y = 20;

    static {
//        x = 30; // compile time error , we can't initialize final variable.
        System.out.println(x);
    }

    {
//        y=80; // compile time error , we can't initialize final variable.
        System.out.println(y); // non-static block
    }
    public static void main(String[] args) {
        new Test();

    }
}
```
 ### ***Output :*** ###
