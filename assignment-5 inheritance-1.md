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
     No, Multiple objects are not created in inheritance hierarchy.
     Only we create the child class referance object.
     Through the child clss referance we can access all the inherited class.


## QUESTION: 5 ##
**Does super constructor invocation creates one more object.?**
### ***Answer :*** ###
     No,super() constructor can't create any new object.
     If it is call the parent() class constructor ,then it will use same class constuctor.
     


## QUESTION: 6 ##
**Code example of method hiding.?**
### ***Output :*** ###


## QUESTION: 7 ##
**Code example of variable hiding.?**
### ***Output :*** ###

## QUESTION: 8 ##
**Does static methods overridden.?**
### ***Answer :*** ###
       No,we can't override the static method().

## QUESTION: 9 ##
**Does private methods overridden.?**
### ***Answer :*** ###
     No, we can't override the static methods.
     It only inherited.

## QUESTION: 10 ##
**By default any class extends which class.?**
### ***Answer :*** ###
      By default any class extends from Object class.
## QUESTION: 11 ##
**List down the public/protected (inherited) methods present in java.lag.Object class.?**
### ***Answer :*** ###
   #### public :- ####
      equals(Object obj),Class<?> getClass(),hashCode(),notify()
      notifyAll(),toString(),wait(),wait(long var1),wait(long timeoutMillis, int nanos)
   #### protected :- ####  
    clone(),finalize()

* **Find the output:**
```java
class A
{
  public int i = 10;
  public int j = 20;
}
class B extends A
{
   public int i = 100;
   public int sumValue(int x)
   {
      return x + this.i + this.j +  super.i + super.j;
   }
}

class Test
{
  public static void main(String[] args)
  {
    A a = new B();
    int result = a.sumValue(a.i);
    System.out.println(result);
  }

}
```
### *** Explanation :*** ###
  * There will be a compilation error because sumValue(int x) method is not present in class A.
  * If we create a sumValue(int x) method in class A then the error can be avoided.
  * If we type cast to [int result = ((B) a).sumValue(a.i);] , then the error can be avoided.
 
 ### *** Output :*** ###
      160


* **Fix the code with all the approaches you know.**
```java
class A
{
  private int i;
  public A(int i)
  {
     this.i = i;
  }
}

class B extends A
{
   public B()
   {
   
   }
}
```
### ***Output :*** ###
  * There will be compilation error at [public B()]
  * If we create no argument constructor inside class A , the error can be fixed.
  * If we call super function with one argument inside constructor B, the error can be fixed.

