<b> C# Built-in Data Types </b>
bool a = true;                // true or false
byte b = 254;                // 0 to 255
sbyte c = -127;             // -128 to 127
char d = 'c';            
string s = "Hello World";
decimal e = 3_000.5m;     //+-1.0 x 10-28 to +-7.928 x 1028(28-29 digits)
double f = 3_000.5D;       //+-5.0 x 10-324 to +-1.7 x 10300 (15-17 digits)
float g = 3_000.5F;          //+-1.5 x 10-45 to +-3.4 x 1028 (6-9 digits)
int h = 12;                         //-2147403640 to +2147403640
unit i = 12;                        // 0 to 4294967295
long i = 1212;                   //-9223372036854775808 to 9223372036854775807
u long m = 121212;         //0 to 18446744073551615
short n = -32768;          //-32768 to 32767
ushort o = 6454;           //0 to 65535

<b>Primitive Data Type </b>
->Data type that are pre-defined by the C# are called primitive data types.

<b>Explicitly typed local variable</b>
->like int a = 1; float b = 12.12; char c ='c';

<b> Implicity typed local variable </b>
-> like var a = "hello"; var b = 12;
-> it can be only declare inside the method as local variable

<b> C# is Type Safe </b>
-> Type validation is done at compile time rather than run time
-> 
```
string username = "Default";
// logic
// user has to enter his username
username = "user entered username";
```

<b>Methods</b>
-> A method is a code block that contains a series of statements. A program causes the statements to be executed by calling the method. The Main method is the entry point for every C# application and it is called by the common language runtime(CLR) when the program is started.

Syntax
```
<Access Specifier><Return Type><Method Name>(Parameter List)
{
  Method Body
}
```
Access Specifier -> The Access Specifier determines the visibility of a variable or a method from another class.
Return Type -> A method may return a value. The return type is the data type of the value the method returns. If the method is not returning any values, then the return type is void.
Method name ->Method name is a unique identifier and it is case sensitive. It cannot be same as any other identifier declared in the class.
Parameter List -> Enclosed between parentheses, the parameters are used to pass and receive data from a method. The parameter lists refers to the type, order , and the number of the parameters of a method. Parameters are optional; that is method may contain no parameters.
Method Body ->This contains the set of instructions to complete the required activity.

->If we call method from static method then the another method should be static.

<b>Catching Error </b>
```
try
{
//logic code
}
catch(Exception)
{
Console.WriteLine("Somethig error")
}
finally
{
 -> here finally is used for -> like whether the try block code is used or catch block code is done -> after that finally code block execute -> if try block or catch block work or not work but now finally is executed
}
```
-> Parse method returns the converted number. Where TryParse  method returns a boolean value that indicates whether the conversion succeeded , and returns the converted number in an out parameter. If the string is not in a valid format , Parse throws an exception but TryParse returns false.
```
bool success = int.TryParse(input_string, out parsedValue);
// here input_string ="18"; can be parsed but not input_string ="18xyz";
```
<b> Loop Types </b>
-> for loops
-> while loop( check and go)
-> do while loop (do first then check)
-> foreach loop (run through array or list)
```
//while loop 
int i =0;
while(condition)
{
//execute code
i++;
}
```
```
//do while
int i =0;
do
{
//execute code
int ++;
}while(condition)
{

}

//foreach loop
->only as long as there is content
```

<b> Class </b>
->A class is a blue print or Template of an Object.
->It has actions/abilities - so called functions or methods
->and it has properties -so called member variables
-> Can be used like a Datatype(eg String is a Class)
-> Class is not a real world Entity -> ex like animals are not real world entity
-> Class does not occupy memory.
```
class Human
{
public string firstName;
public string lastName;
public void introduceMyself()
{
Console.WriteLine("My name is {0} {1}", firstName, lastName);
}
}
```


<b>Object</b>
-> Object is an instance of Class.
->Object occupy memory.
-> Object is a real world entity like dog, cat which can we see in the real world.
```
Human Pawan = new Human(); //to make object from class Human
Pawan.firstName = "Pawan";
Pawan.lastName = "Kunwar";
Pawan.introduceMyself();
```
<b> Constructors </b>
-> Constructors are called when object is created.
-> Constructors should be same as class name.
->It does not contain any data type.
-> Default constructor are made by compiler when Class is made.
```
class Human
{
public string firstName;
public string lastName;

public Human() // also called defalult constructor
{
 Console.WriteLine("Object creater , constructor created");
}

public Human(string myFirstName, lastName) // also called parameterized constructor
{
firstName = myFirstName;
this.lastName = lastName;
}
public void introduceMyself()
{
Console.WriteLine("My name is {0} {1}", firstName, lastName);
}
}


Human Pawan = new Human("Pawan", "Kunwar");
Human noHuman = new Human();

this type constructor are used because when some user have all values like first name , last name , address but some user do not have address. so based on that things we create different constructors for class.
```
<b> Destructors </b>
->One class only can have one destructor or finalizer
```
~Members()
{

}
```


<b> Properties </b>
-> Property allow we to control the accessibility of a class variables and are the recommended way to access variables from the outside in C#.
-> Importances
a) Encapsulation
b) Data Validation

Types 
a) Read/Write Properties
b) Read Only Properties
c) Write Only Properties
d) Auto Implemented Property -> `public int Id{get; set;}`
```
public C
{
public int Id{get; private set;}
public Id(int id)
{
Id = id;
}
main()
{
C prop = new C(12); -> if we set the private set then it can only set the value from its own constructor 
prop.Id = 12; -> but not this way
}
}
```


-> Property start with Capital Letter
Getters and Setters 
```
class Program
{
  static void Main(string[] args)
  {
     Car car = new Car();
     car.title = "Hero Honda";
     Conosle.WriteLine(car.title);
  }
}
class Car
{
public string title;
}
--> This breaks the principle of OOP abstraction by directly accessing the another class member variable. So we used setter and getter.


//this is the old method for setter and getter 
class Program
{
  static void Main(string[] args)
  {
     Car car = new Car();
     car.title = "Hero Honda";
     Conosle.WriteLine(car.title);
  }
}
class Car
{
private string title;
}
public string GetTitle()
{
return title;
}
public void SetTitle(string value)
{
title = value;
}

//another way
class Program
{
  static void Main(string[] args)
  {
     Car car = new Car();
     car.Title = "Hero Honda";
     Conosle.WriteLine(car.Title);
  }
}
class Car
{
private string title;
}
public string Title
{
get
{
return title;
}
set
{
title = value; -> here value is assigned to title when Title is called
}
}

//Best way 
main()
{
Car two = new Car();
two.Type = "Car11";
Console.WriteLine(two.Type);
}

class Car
{
public string Type {get; set;} //it will automatically make the private variable and do get and set
}
```
<b> Arrays</b>
```
int[] grades = new int[5]; //integer array name grades containing 5 elements.
int[] grades = {10,20,30};
int[] grades = new int[]{12,20,30,40};

foreach(int k in grades)
{
Console.WriteLine("{0}",k)
}
```
<b>2D Arrays</b>
```
string[,] matrix; 
```
<b>3D Arrays </b>
```
string[,,] matrix;
```
<b>Jagged Array</b>
-> Array inside Array 
```
int[][] jaggedArray = new int[][]
{
new int[]{2,3,4,5,6};
new int[]{1,2,3};
}
```
<b>ArrayList</b>
```
We can use ArrayList class by using 
//declaring an ArrayList with undefined amount of object
ArrayList myArrayList = new ArrayList();
//declaring an ArrayList with defined amount of object
ArrayList myArrayList = new ArrayList(100);

myArrayList.Add(25);
myArrayList.Add("hello");
myArrayList.Add(25.12);
//delete element with specific value from the arrayList
myArrayList.Remove(25);
//delete element at specific position
myArrayList.RemoveAt(0);
```
<b> Value Type and Reference Type </b>
Structure -> Value Type -> Stack Memory
Class -> Reference Type -> Heap Memory
Value Type's object is created at Stack
Reference Type's object is created at Heap
In Value Type -> reference variable is created at stack and object is also created at Stack.
In Reference Type -> reference variable is created at stack but object is created at Heap.
Advantages of References Type is that reference variable is created at stack so it take less memory but object is made at Heap 
->Reference Type do memory management. 
-> In Value Type, Memory is allocated at compile time but In Reference is allocated at run time.

->A data type is a value type if it holds a data value within its own memory space. It means variable of these data types directly contain their values. Ex-> bool, byte short etc also called primitive data types.

->Unlike value types, a reference type does not store its value directly. instead it stores the address where the value is being stored. In other words, a reference type contains a pointer to another memory location that holds the data. Ex-> String , All arrays, even if their elements are value types, Class, Object, Delegates, Interface.

--> When we create a new object of Child class using Parent reference then we only can access members and function of Parent Class . but when we create Child object using Child reference we can access both Parent and Child members and methods.
-> `C c = new C();` -> If we know exact runtime type of object then we should use this approach. 
-> `P p = new C();` -> If we don't know exact runtime of an object then we should use this approach.