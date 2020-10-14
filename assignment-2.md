# ASSIGNMENT-2 #
 ## QUESTION: 1 ##
**Example with code to show state and behaviour of an object
       where behaviour depends upon the state of object?**
  ### Program : ###
   ```java 
    package org.assignment.phone;

public class MobilePhone {
    // states of mobilephone class
    private String mobName;
    private String mobModel;
    private String mobColor;
    private double mobPrice;


    MobilePhone(String mobName, String mobColor, double mobPrice) {
        //inside constructor initialization of object state
        this.mobName = mobName;
        this.mobColor = mobColor;
        this.mobPrice = mobPrice;
        this.mobileInfo(this); //object behaviour

    }

    public void mobileInfo(MobilePhone mob) {
        mob.mobName = this.mobName;
        this.mobModel = "Android 1951";

        System.out.println(mob.hashCode() == this.hashCode());

        System.out.println("\nThe Mobile Name is : " + mob.mobName);
        System.out.println("The Mobile Name is : " + mobName);
        System.out.println("\nThe Mobile Price is : " + mob.mobPrice);
        System.out.println("The Mobile Price is : " + mobPrice);
        System.out.println("\nThe Mobile Model is : " + mob.mobModel);
        System.out.println("The Mobile Model is : " + mobModel);
        System.out.println("\nThe Mobile Color is : " + mob.mobColor);
        System.out.println("The Mobile Color is : " + mobColor);

        System.out.println("\nAfter discount The cost is : " + discount(this) + "\n \n");
        System.out.println("----------------------------------------------------------------------------------------");

    }

    public double discount(MobilePhone t1) {

        return t1.mobPrice = mobPrice - 500;

    }

}


package org.assignment.phone;

public class MobilePhoneMain {
    public static void main(String[] args) {
        MobilePhone mobilePhone = new MobilePhone("Vivo", "Sonic Blue", 28569.49); // constuctor called
        MobilePhone mobilePhone1 = new MobilePhone("Sumsung", "Rosy Pink", 20569.49);
        mobilePhone.mobileInfo(mobilePhone1);
    }
}
```
### ***Output :*** ###
        true
        
        The Mobile Name is : Vivo
        The Mobile Name is : Vivo

        The Mobile Price is : 28569.49
        The Mobile Price is : 28569.49

        The Mobile Model is : Android 1951
        The Mobile Model is : Android 1951

        The Mobile Color is : Sonic Blue
        The Mobile Color is : Sonic Blue

        After discount The cost is : 28069.49
        ----------------------------------------------------------------------------------------
        true
        
        The Mobile Name is : Sumsung
        The Mobile Name is : Sumsung

        The Mobile Price is : 20569.49
        The Mobile Price is : 20569.49

        The Mobile Model is : Android 1951
        The Mobile Model is : Android 1951

        The Mobile Color is : Rosy Pink
        The Mobile Color is : Rosy Pink

        After discount The cost is : 20069.49
        ----------------------------------------------------------------------------------------
        false

        The Mobile Name is : Vivo
        The Mobile Name is : Vivo

        The Mobile Price is : 20069.49
        The Mobile Price is : 28069.49

        The Mobile Model is : Android 1951
        The Mobile Model is : Android 1951

        The Mobile Color is : Rosy Pink
        The Mobile Color is : Sonic Blue

        After discount The cost is : 27569.49
        ----------------------------------------------------------------------------------------


## QUESTION:2 ##
**What is the definition of hashcode as per java 8 document?**
 ### ***Answer :*** ###
- **hashCode() :-**
  -------------------
    The hashCode() method is defined in Object class which is the super most class in Java.
    This method returns a hash code value for the object. 
    
    * It returns an integer value of the object memory address.
    * It is a native method.
    * The hashCode() method should return a unique value for every object.
    * If two objects are equal according to equals() method, then their hash code must be the same.
    * It is not required that if two objects are unequal according to the equals(java.lang.Object) method,
      then calling the hashCode method on each of the two objects must produce distinct integer results.
      However, the programmer should be aware that producing distinct integer results for unequal objects may improve the performance of hash tables.
## QUESTION:3 ##
**What is the fully qualified name of Object class in java ?**
 ### ***Answer :*** ###
   - The fully qualifued Object Class in java is ***java.lang.Object*** .

## QUESTION:4 ##
 **Object class is in which package ?**
  ### ***Answer :*** ###
   - It is in **java.lang** package.
 
 
#  Find the output? Always write the explanation for the output. why you are getting that output? #
 
## **1.**  **Find the output?** ##
```java
  public class Test {
    public static void main(String[] args) {
        Object obj1 = new Object();
        Object obj2 = new Object();
        System.out.println(obj1.hashCode() == obj2.hashCode());
        System.out.println(obj1.getClass());
        System.out.println(obj1 == obj2);
    }
}
```
### ***Answer :*** ###

* false ,Because different **object** have different ***hashcode***.

* class java.lang.Object  ***object*** is fully clasified class of - **java.lang package** .

* false  ***== operator*** compare the memorylocation here obj1 and 
obj2 has different memory location because obj1 and obj2 have different hashcode.

## **2.** **Find the output?** ##
```java
public class Test {
    int x;

    public Test(int x) {
        this.x = x;
    }

    public static void main(String[] args) {
        Test t = new Test(10);
        System.out.println(t.x);
    }
}
```
### ***Answer :*** ###
*  10 
* when we create an object, here the one argument constuctor is automatically called and the value of X will be assign 10.


## **3.** **Why below code will not compile?What is the fix we have to do so that the code will compile?** ##
```java
public class Test {
    int x;

    public Test(int x) {
        this.x = x;
    }

    public static void main(String[] args) {
        Test t = new Test();
        System.out.println(t.x);
    }
}
```
### ***Answer :*** ###

* No,It gives compile time error.
* Because here at the constuctor calling part, we have not passed any value of type ***int***.


 
## **4.** **Will below code will compile?** ##
```java
public class Test {
    int x;

    public Test(int x) {
        this.x = x;
    }

    public Test() {

    }

    public static void main(String[] args) {
        Test t = new Test();
        System.out.println(t.x);
    }
}
```
### ***Answer :*** ###

* Yes, the above code will be compile .Because,  we define no argument constuctor as well as 
one parameterize constuctor and the O/P is **0** (default value of int).


## **5.** **Find the output?** ##
```java
public class Test {
    int x;
    String y;

    public static void main(String[] args) {
        Test t = new Test();
        System.out.println(t.x);
        System.out.println(t.y);
    }
}
```
### ***Answer :*** ###

* 0  // Here, X is not initialized so default value of **int 0**.
* null // Y  is not initialized so default value of **String null**.


       
## **6.** **What is the default value of int,String variables?** ##
### ***Answer :*** ###
      
      Default value of int = 0
      Default value of String = null
 
## **7.** **Find the output?** ##
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        this.x = x;
        this.y = y;
        Test tVar = this;
        System.out.println(tVar.hashCode() == this.hashCode());
    }

    public static void main(String[] args) {
        Test t = new Test(10, "john");
        System.out.println(t.x);
        System.out.println(t.y);
    }
}
```
### ***Output :*** ###

* true // **Test tVar=this;** Here **this** refers to current object and it will assigned to tVar so,it
address same memory locaion. 
* 10
* john

## **8.** **Find the output?** ##
```java    

public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        this.x = x;
        this.y = y;
        m1(this);
    }

    public static void main(String[] args) {
        Test t = new Test(10, "john");
        System.out.println(t.x);
        System.out.println(t.y);
    }

    public void m1(Test t1) {
        t1.x = 100;
        t1.y = "Doe";
    }
}
```
### ***Output :*** ###
* 100
* Doe
* Here **m1(this);** will be invoke ***m1()*** and the field value X or Y are updated from 10, john to 100 and Deo.



## **9.**  **Find the output?** ##
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        this.x = x;
        this.y = y;
        this.m1(this);
    }

    public static void main(String[] args) {
        Test t = new Test(10, "john");
        System.out.println(t.x == 10);
        System.out.println(t.y == "john");
    }

    public void m1(Test t1) {
        t1.x = 100;
        t1.y = "Doe";
    }
}
```
### ***Output :*** ###
  * false this.m1(this); ]  
  *  false                                    
  *  Here,**this.m1(this);**  upadate   x=100 and  y=Deo so, t.x==10 and t.y==john will the result is ***false***

## **10.** **Find the output?** ##
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        x = x;
        y = y;
        this.m1(this);
    }

    public static void main(String[] args) {
        Test t = new Test(10, "john");
        System.out.println(t.x);
        System.out.println(t.y);
    }

    public void m1(Test t1) {
        t1.x = 100;
        t1.y = "Doe";
    }
}
```
### ***Output :*** ###
* 100 
* Deo
* Here, x = x and y = y will not modify the field value but ***m1(this)*** update the field value x and y.
     
## **11.** **Find the output?** ##
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        x = x;
        y = y;
    }

    public static void main(String[] args) {
        Test t = new Test(10, "john");
        System.out.println(t.x);
        System.out.println(t.y);
    }

    public void m1(Test t1) {
        t1.x = 100;
        t1.y = "Doe";
    }
}
```
### ***Output :*** ###
     0
     null
      
## **12.** **Find the output?** ##
```java
public class Test {
    int x;
    String y;

    public Test(int x, String y) {
        x = x;
        y = y;
    }

    public static void main(String[] args) {
        Test t = new Test(10, "john");
        Test t1 = t;
        System.out.println(t1 == t);
        t1.x = 300;
        t1.y = "alex";
        System.out.println(t.x);
        System.out.println(t.y);
    }
}
```

### ***Output :*** ###
* true  
* Here, **Test t** is assign to **t1**.So both are refers to same memory location and field are also same so its ***true***.
* 300
* alex



## **13.** **Identify State&Behaviour.Find where the state is used.Does behavour depends on the state?** ##
```java
public class Calculator
{
   private int i;
   private int j;
   
   public Calculator(int i, int j)
   {
     this.i = i;
     this.j = j;
   }
   
   public int sum()
   {
     return i + j;
   }
}
```
### ***Output :*** ###

  *  private int i;  // state 
     private int j;  // state 
    
   * this.i = i; // state of an object
     this.j = j; // state of an object

   * int sum() //behaviour
     return i + j; //here object behaviour depends upon state

 
## **14.** **Find the output?Identify the static method&variables.** ##

```java
public class Test 
{
    static int x;
    int y;

    static 
    {
        x = 10;
    }

    static
    {
        x = x + 20;
    }

    {
        y = 100;
    }

    {
        y = y + 20;
    }

    public static void main(String[] args) {
        Test t = null;
        t.x = t.x + 40;
        x = x + 50;

        t = new Test();
        t.y = t.y + 200;

        Test t1 = new Test();
        System.out.println(t.x);
        System.out.println(t1.x);
        System.out.println(Test.x);

        System.out.println(t.y);
        System.out.println(t1.y);

        System.out.println(t.getX());
        System.out.println(t1.getX());
        System.out.println(Test.getX());

        System.out.println(t.getSum());
        System.out.println(t1.getSum());

    }

    public static int getX() {
        return x;
    }

    public int getSum() {
        return x + y;
    }
}
```
### ***Output :*** ###
  * 120
    120
    120
    320
    120
    120
    120
    120
    440
    240
* In the above code, **int getX()** is the static method and here,**x is stactic variable** and **y is non-static variable** .

 ## **15.** **Write some code to create Null Pointer Exception?** ##
 ### ***Program :*** ###
 ```java
        
    public class Test1 {
    static int x;
    void m1(){
        System.out.println("Inside m1 method");
    }
    public static void main(String[] args) {
        Test1 obj=null;
        obj.x=x+20;
        obj.m1(); // In this line occurs nullPointerException of  java.lang.NullPointerException class

    }
}
```

