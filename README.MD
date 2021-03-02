# IS 219 Calculator
[![Coverage Status](https://coveralls.io/repos/github/ChinonsoChima/IS219CalcNew-master/badge.svg?branch=master)](https://coveralls.io/github/ChinonsoChima/IS219CalcNew-master?branch=master)
[![Build Status](https://travis-ci.org/ChinonsoChima/IS219CalcNew-master.svg?branch=master)](https://travis-ci.org/ChinonsoChima/IS219CalcNew-master)
<br>
<br>
<h3>Design Patterns</h3>

<h4>
Creational - Builder: This creational design pattern allows programmers to build 
a complex object using simpler objects and using a step-by-step 
approach. This helps produce different types and representations 
of an object using the same construction code. The Builder pattern allows a collection of 
builders to do its own separate operation to build to 
the overall object. For example, in our calculator app, we had 
Calculator.js, Calculation.js, and the other operational files
(Addition.js, Subtraction.js, etc). Here, the operational files 
would be the builders for the Calculator app. It is divided into 
different functionalities and products that will make up the 
calculator app to deliver the proper functions that the client 
needs. And often in a Builder pattern, it is recommended that 
there be a Director object that controls/manages what kinds of 
Builders to call. In our app, we can view the Calculation.js file 
as our manager as it calls what kinds of operations to run by 
passing the type of operation as one of its variables.
<br><br>

Structural - Decorator: allows a user to add new functionality to an 
existing object without altering its structure. This type of design
pattern comes under structural pattern as this pattern acts 
as a wrapper to existing class. This pattern creates a decorator class which 
wraps the original class and provides additional 
functionality keeping class methods signature intact.
<br><br>

Behavioral - Chain of Responsibility: is a behavioral design 
pattern that lets you pass requests along a chain of handlers. 
Upon receiving a request, each handler decides either to process 
the request or to pass it to the next handler in the chain.
<br><br>


</h4>
<br><br><h3>The 4 Principles of OOP (Object-Oriented Programming)</h3><br>
<p>

1. Encapsulation - defined as the wrapping up of data under a single unit. It is the 
   mechanism that binds together code and the data it manipulates. 
   Another way to think about encapsulation is, it is a protective shield 
   that prevents the data from being accessed by the code outside this shield.<br><br>
   
2. Abstraction - defined as displaying only the essential details to the user.
   The trivial or the non-essentials units are not displayed to the user.<br><br>

3. Inheritance - Inheritance is an important pillar of Object-Oriented Programming. 
   It is the mechanism in by which one class is allowed 
   to inherit the features(fields and methods) of another class. <br><br>

4. Polymorphism - The word polymorphism means having many forms. In simple words, we can define 
   polymorphism as the ability of a message to be displayed in 
   more than one form.It is useful when using inheritance. When the child 
   has the same inherited methods as the parent, 
   but the child wants to define its own functionality for that specific method, 
   we can use polymorphism.<br><br>
</p><br>

<h3><b>S.O.L.I.D.</b> Principles</h3>
<p>
1. S - Single Responsibility Principle: This means that every function 
you write should have one purpose.
For example we see that this sum function does one thing.

```
function Sum (a,b) {
    return a + b;
}
```
This function just adds two numbers and nothing else.<br><br>

2. O - Open-Closed Principle: This means that your code should
   be open for extension but closed for modification. In simpler terms, it
   means that no one should have to go into the file where your code is
   to modify it in order to use it. For example:
   ```
   let iceCreamFlavors = ['chocolate', 'vanilla'];
   let iceCreamMaker = {
      makeIceCream(flavor) {
         if (iceCreamFlavors.indexOf(flavor) > -1) {
            console.log('Great success. You now have ice cream.');
         } else {
            console.log('Epic fail. No ice cream for you.');
         }
      },
      addFlavor(flavor) {
         iceCreamFlavors.push(flavor);
      },
   };
   export default iceCreamMaker;
   ```
   In this code, the ```iceCreamFlavors``` array already has
    some values inside already. But with the ```addFlavor``` function,
    you can add more flavors without having to go inside the code
   and modify it.<br><br>
   
3. L - Liskov Substitution Principle: This principle says that a parent
   class and a child class can be interchanged without breaking your program.
   For example:
   ```
   class TrasportationDevice
   {
      String name;
      String getName() { ... }
      void setName(String n) { ... }
      double speed;
      double getSpeed() { ... }
      void setSpeed(double d) { ... }
      
      Engine engine;
      Engine getEngine() { ... }
      void setEngine(Engine e) { ... }
   
      void startEngine() { ... }
   }
   class Car extends TransportationDevice
   {
      @Override
      void startEngine() { ... }
   }
   
   ```
   the ```Car``` class overrides the ```startEngine``` method
   from the ```TransportationDevice``` class with no problem,
   meaning that you could switch between the classes without breaking
   the program.<br><br>
   
4. I - Interface Segregation: this principle states that no client should be 
   forced to depend on methods it does not use. Basically, don't have
   unnecessary code and make sure every function in your code is useable.<br><br>
   
5. D - Dependency Inversion Principle: This priciple states that "High-level modules should not depend on low-level modules. Both should depend on abstractions."

If we look at the Calculator class we see one line that is used to specify which operation we are using bewteen two numbers

```
let calculation = Calculation.Create(a,b,Product);
```
Where you see the Product paramter, that can be changed to any other 
operation that is created in the Operations folder 
without having to rely on the create function in the Calculation class

This shows how Calculator class does not depend on the Calculation class to figure out what operation to use.<br>

</p>