-> Abstract Methods -> Methods without method body
-> Interfaces can only contains Abstract Methods.
-> Interfaces are user-defined data types.
-> Interfaces initialize methods and Class implement that methods -> It is defined by `interface` keyword like `IDog`

->Like child class inheritance member variable  and methods to consume from Parent Class -> Child class also inheritance from Interfaces to implement the members  -> Every abstract method of an interface should be implemented by the child class of the Interface and it should be implemented compulsory or strictly.

-> A Class can inherit from a class and interface at a time.
```
<modifiers> interface <interfaceName>
{
-
}
```

-> The default scope the members of an interface is public whereas it's private in Class.

->To define a abstract method in Class
```
public abstract Add(int a, int b);
```
-> To define a abstract method in Interface
```
Add(int a , int b); //by default every member or method of an interface is abstract
```
-> We cannot declare any fields/variables in Interface.

-> If required an Interface can inherit form another Interface
```
example
interface ITest
{
void Add();
}
interface ITest1 : ITest
{
void Sub();
}

class Implementation : ITest
{
public void Add() // here we add public 
{
}
class Implementation1 :ITest1
{
void ITest1.Add()
{
}
public void Sub()
{
}
}

}
```
