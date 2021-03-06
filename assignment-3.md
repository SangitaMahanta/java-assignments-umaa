# ASSIGNMENT-3 #

## QUESTION:1 ##

 **Write a simple example of a Product class where it uses this constructor with paremeterized constructor.**
 ### ***Solution :*** ###
  ```java
  public class Product {
    private String fruit;
    private double amount;
    private double price;

    Product(String fruit, double amount, double price) {
        this(amount, price);
        this.fruit = fruit;
        display(this);

    }

    Product(double amount, double price) {
        this.amount = amount;
        this.price = price;
    }

    void display(Product t) {
        System.out.println("Fruit name is = " + fruit + " of amount = " + amount + " is of price =" + price);

    }

    @Override
    public String toString() {
        return "Product{" +
                "fruit='" + fruit + '\'' +
                ", amount=" + amount +
                ", price=" + price +
                '}';
    }


    public static void main(String[] args) {
        Product product = new Product("Apple", 2.5, 400);
        System.out.println("----------------------------------------------------");
        String result = product.toString();
        System.out.println(result);
        System.out.println("----------------------------------------------------");
        Product product1=new Product("Orange",3,350);


    }
}
```
### ***Output :*** ###
	Fruit name is = Apple of amount = 2.5 is of price =400.0
	----------------------------------------------------
	Product{fruit='Apple', amount=2.5, price=400.0}
	----------------------------------------------------
	Fruit name is = Orange of amount = 3.0 is of price =350.0


  
  
## QUESTION:2 ##

 **Does toString() method present in java.lang.Object class? If yes what the implementaion for toString() method given by java.lang.Object class.**
 ### ***Answer :*** ###
  - Yes, the toString() present in java.lang.Object class.
  - It returns the ***string***  representation of an object . It means , it consisting of the class of which
  the object is an instance, the at-sign character ***`@`***, and the unsigned hexadecimal representation of the
  ***hashCode*** of that object.
  
## QUESTION:3 ## 
 
  **Override toString() method in the class A (as given below) such that it will print the value of i, j, k.**
```java
    public class Test 
    {
        public static void main(String[] args)
        {
            A a = new A(10, 20);
            a.setK(400);
            System.out.println(a);
        }
    }

    class A {
        private int i;
        private int j;
        private int k;

        public A(int i, int j) 
        {
            this.i = i;
            this.j = j;
        }

        public int getI()
        {
            return i;
        }

        public void setI(int i)
        {
            this.i = i;
        }

        public int getJ()
        {
            return j;
        }

        public void setJ(int j)
        {
            this.j = j;
        }

        public int getK()
        {
            return k;
        }

        public void setK(int k)
        {
            this.k = k;
        }
    }
 ```
 
  - *After using ***Override toString()*** the code is :*
   ```java
   public class Test {
    public static void main(String[] args) {
        A a = new A(10, 20);
        a.setK(400);
        System.out.println(a);
    }
}

class A {
    private int i;
    private int j;
    private int k;

    public A(int i, int j) {
        this.i = i;
        this.j = j;
    }

    public int getI() {
        return i;
    }

    public void setI(int i) {
        this.i = i;
    }

    public int getJ() {
        return j;
    }

    public void setJ(int j) {
        this.j = j;
    }

    public int getK() {
        return k;
    }

    public void setK(int k) {
        this.k = k;
    }
    
     @Override
    public String toString() {
        return "A{" + "i =" + i + ", j=" + j + ", k=" + k + "}";
    }
}
```
### ***Output :*** ###
     A[i =10, j =20, k =400]
     Here, the overriden toString() helps to getting an object states.

## QUESTION:4 ##  
   **What is StackOverflowError. When it occurs. It comes under which package in java library.**

### ***Answer :*** ###
   
   - A  StackOverflowError is a runtime error in java.
   - It is thrown when the amount of call stack memory allocated by JVM is exceeded, due to excessive deep
   loop or infinite recursion.
   - It comes under java.lang.StackOverflowError package in java library.
   
## QUESTION:5 ##  
   **Will the below code compile? Find the output of the below code.** 
   ```java
            public class Test {
            public static void main(String[] args) {
                A a = new A();
            }
        }

        class A
        {
            private int x =11;
            public A()
            {
                new A(10);
            }

            public A(int x) 
            {
                this();
                this.x = x;
            }
        }
```
    
     
   ### ***Answer :*** ### 
   - Yes, the above code will compile.But there is a recursion between **this()** and **A(int x)** meethods so, it wiil throw error at runtime thats is called StackOverFlowError.
   
 

## QUESTION:6 ##         
   **Will the below code compile. If not why?**
  ```java
class A
{
    private int x =11;
    public A()
    {
        this(10);
    }

    public A(int x)
    {
        this();
        this.x = x;
    }
}
```
 ### ***Answer :*** ###
    No , It will not compile.Because here no main() is present.
    If we create main() then it also throw  recursive constructor invocation error in compile time.
## QUESTION:7 ##    
 **Find the output with explanation.**
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
    }
}

class A
{
    private int x =11;
    public A()
    {
        this(10);
        if(x % 2 == 0)
        {
            System.out.println("even");
        }
        else
        {
            System.out.println("odd");
        }
    }
    
    public A(int x)
    {
        this.x = x;
    }
}
```
### ***Output :*** ###
- even
### ***Explanation :*** ###
- Within ***main()*** constructor A() is called , And inside constructor A() ***this(10);*** which is invoking one parameterized constructor, inside that constuctor the value of ***x*** will be updated to 10 and  ***10%2 = 0***  ,so the output is ***even*** .
 ## QUESTION:8 ##   
 **Will the below code compile?**
```java
class A
{
    public A()
    {
        new A();
    }
}
```
### ***Answer :*** ###
    Yes,It will compile. But it will gives StackOverFlowError at runtime.
## QUESTION:9 ##   
 **Why the below code won't compile?**
```java
class A
{
    public A()
    {
        this();
    }
}
```
### ***Explanation :*** ###
    The above code will throw compile time error,Because of recurrsive contructor invokation.

## QUESTION:10 ##   
 **Find the output with explanation?**
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
        System.out.println(a.hashValue == a.hashCode());
    }
}

class A
{
    public int i;
    public int hashValue;
    public A()
    {
        new A(10);
    }

    public A(int x)
    {
        this.i = x;
        this.hashValue = this.hashCode();
    }
}
```
### ***Output :*** ###
     false
     
### ***Explanation :*** ###
   - Inside class Test, we create an object of **class A** and assigned to instaance variable **a** ,in that time a zero argument constuctor will be called.
   - But within zero argument constuctor , a newly created object of one argument constuctor will be invoked. so
   here, this.hashcode has assigned to this.hashValue.It will only update the value of field hashValue only for
   newly created object.It will not update the feild value of raferance object **a** .So the value of a.hashValue  
   and a.hashCode() are not equal, So the ouput is false.
  
  
## QUESTION:11 ##  
 **Find the output with explanation?**
```java
public class Test {
    public static void main(String[] args) {
        A a = new A();
        System.out.println(a.hashValue == a.hashCode());
    }
}

class A
{
    public int i;
    public int hashValue;
    public A()
    {
        this(10);
    }
    
    public A(int x)
    {
        this.i = x;
        this.hashValue = this.hashCode();
    }
    
}
```
### ***Output :*** ###
    true
### ***Explanation :*** ###
  - Here, within constuctor **A()**, invoked one argument constructor **this(10)** which has update the  feild value of that object and hold ***hashCode*** value .
  - so, The value of a.hashValue and a.hashCode() are equal. So the ouput is "true".
## QUESTION:12 ## 
 **Access Modifiers & Packages. Find the compilation errors & why? Find the output also by fixing them.**
```java
package com.pkg1;

class A
{
  private int i = 10;
  public int j = 100;
  int k = 50;
}

package com.pkg1;
class B
{
  public static void main(String[] args)
  {
    A a = new A();
	System.out.println(a.i);
	System.out.println(a.j);
	System.out.println(a.k); // why this is accessible?
  }
}

package com.pkg2;
class B
{
  public static void main(String[] args)
  {
    A a = new A();
	System.out.println(a.i);
	System.out.println(a.j);
	System.out.println(a.k); // why this is not accessible?
  }
}
```
 ### ***Answer :*** ###
   - Here, in package **com.pkg1** field **i** is private.So we can't access the field **i** in class B from class A ,in same package.
   Because private field can't be accessed in another class.
   - So,to avoid the error we have to create a **gatter()** for **i** inside class A and call **i** through that **gatter()** inside class B.
   - In package, **com.pkg2** we have called class A.But there is no class A inside package **com.pkg2**.
   - So,we have to import class A from package **com.pkg1**.
   - Here, in package **com.pkg2** field **i & k** can not be accessible .Because,in different package **private And default** field can not b accessible.
   - We have to create **getter()** inside class A of package **com.pkg1** and print **i & K** inside class B of package **com.pkg2** through that **getter()** .
   
   ```java
   package org.assignment.com.pkg1;

public class A {
    private int i = 10;
    public int j = 100;
    int k = 50;

    public int getI() {
        return i;
    }

    public int getK() {
        return k;
    }
}

package org.assignment.com.pkg1;


public class B {
    public static void main(String[] args)
    {
        A a = new A();
        System.out.println(a.getI());
        System.out.println(a.j);
        System.out.println(a.k); // why this is accessible?
    }
}

package org.assignment.com.pkg2;

import org.assignment.com.pkg1.A;

public class B {
    public static void main(String[] args)
{
    A a = new A();
    System.out.println(a.getI());
    System.out.println(a.j);
    System.out.println(a.getK()); // why this is not accessible?
}
}
```
 ### ***Output :*** ###
 	10
	100
	50
	[ OUTPUT is same for both package ]
 
   
 ## QUESTION:13 ## 
 **Why we use getters and setters for a class. Give an example.**
 ### ***Answer :*** ###
 - Setter is used to set/update the field values of an object.
 - Getters are used to get/retrive the field values.
 ### ***Example :*** ###
 ```java
 public class StudentInfo {
    private String name;
    private int age;
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public void display() {
        System.out.println("name: "+getName());
        System.out.println("age: "+getAge());
    }
}
public class AccessData{
    public static void main(String args[]) {
        //Reading values from user
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the name of the student: ");
        String name = sc.nextLine();
        System.out.println("Enter the age of the student: ");
        int age = sc.nextInt();
        //Calling the setter and getter methods
        StudentInfo studentInfo = new StudentInfo();
        
        studentInfo.setName(name);
        studentInfo.setAge(age);
        studentInfo.display();
    }
}

 ```
 ### ***Output :*** ###
- Enter the name of the student: miki
- Enter the age of the student: 22
- name: miki
- age: 22
 
## QUESTION:14 ## 
 **Why it is good to have private fields with public getters & setters?**
 ### ***Answer :*** ###
     By providing setter ,getter we have better control over the data and we can make sure that data integrity is maintained,so we keep instance variables(data) as private and provide public methods(API) to access them ,in a class.
     
     It maintain the encapsulation concept also.
     

