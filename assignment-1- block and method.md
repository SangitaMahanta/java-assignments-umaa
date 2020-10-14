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
