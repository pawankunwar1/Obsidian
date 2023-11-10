-> Delegate is a type which holds a methods reference in an object.
-> It is also called function pointer.
-> Delegate is of reference type.
->  We use Delegate for Encapsulation -> not giving the methods for direct use by other class
-> It is also used when a class have a lots of function and we can use by them by only one object also.
-> Delegates have no implementation means with no body{}.
-> Using Delegates , we can call any method, which is identified only at run time.
-> To associate a delegate with a particular method, the method must have the same return type and parameter type as that of the Delegate.
-> Delegate makes the application execution time faster which make application faster.
```
namespace DELEGATES_2
{
public delegate void Calculation(int a, int b);
class Program
{
  public static void Addition(int a, int b)
  {
  int result = a + b;
  Console.WriteLine(result);
  }
  public static void Substraction(int a, int b)
  {
  int result = a + b;
  Console.WriteLine(result);
  }
}
}
public static void Main()
{
   Calculation obj = new Calculation(Program.Addition);
   obj(10,20); or obj.Invoke(10,20);
   or another methods for many functions
obj = Substraction;
obj(10,20);

   
}
```
