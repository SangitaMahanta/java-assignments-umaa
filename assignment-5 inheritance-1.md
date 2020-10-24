# ASSIGNMENT-5 #
 ## QUESTION: 1 ##
**Code example of inheritance. Reuse static/non-static method(s) & static/non-static variable(s).?**
  ### Program : ###
  ```java
  
package org.assignment.activity8;

public class TestParent {
    public static int x =12; // static variable
    public int y;// non-static variable


    public void m2(){
        y=10;
        System.out.println("parent class non-static m2()");
        System.out.println("parent non-static variable y =  "+y);
    }
    public static void m1(){
        System.out.println("parent class static m1()");
        System.out.println("parent static variable x = "+x);

    }
}
 class TestChild extends TestParent{
    public void m2(){
        y=100;
        System.out.println("child class non-static m2() ");
        System.out.println("child   y = "+y);
    }
public static void m1(){
        x=90;
    System.out.println("child class static m1() ");
    System.out.println("child x =  "+x);
}
}


package org.assignment.activity8;


import static org.assignment.activity8.TestParent.m1;

public class InheritanceMain {
    public static void main(String[] args) {

        // parent reference variable of child object
        TestParent obj = new TestChild();
       m1(); // parent m1()
        obj.m2(); // child m2()


        TestChild obj1=new TestChild();
        obj1.m1();//child m1()
//        obj1.m2();// child m2()


    }
}
```
### ***Output :*** ###
    parent class static m1()
    parent static variable x = 12
    child class non-static m2() 
    child   y = 100
    child class static m1() 
    child x =  90
  
## QUESTION: 2 ##
**Code example of instance of operator using classes as BaseParent->Parent->Child.?**
  ### Program : ###
  ```java
  ```
  
## QUESTION: 3 ##
**Code example of super constructor.?**
  ### Program : ###
  ```java
  package org.assignment.activity10;

class X {
    X() // parent class constructor
    {
        System.out.println("X() : parent class ");
    }
}

class Y extends X {
    Y() {
        super(); // super() constructor
        System.out.println("Y() : child class ");
    }

    X fun() {
        X obj1 = new X();
        return obj1;
    }
}

public class Test {
    public static void main(String[] args) {
        Y obj = new Y();
        obj.fun();
    }
}
```
### ***Output :*** ###
    X() : parent class 
    Y() : child class 
    X() : parent class 


## QUESTION: 4 ##
**Does multiple object created in inheritance hierarchy.?**
### ***Answer :*** ###


## QUESTION: 5 ##
**Does super constructor invocation creates one more object.?**
### ***Answer :*** ###


## QUESTION: 6 ##
**Code example of method hiding.?**
### ***Output :*** ###


## QUESTION: 7 ##
**Code example of variable hiding.?**
### ***Output :*** ###

## QUESTION: 8 ##
**Does static methods overridden.?**
### ***Answer :*** ###

## QUESTION: 9 ##
**Does private methods overridden.?**
### ***Answer :*** ###

## QUESTION: 10 ##
**By default any class extends which class.?**
### ***Answer :*** ###

## QUESTION: 11 ##
**List down the public/protected (inherited) methods present in java.lag.Object class.?**
### ***Answer :*** ###
