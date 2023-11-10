<h1>HOW FUNCTION CALLS WORK IN LANGUAGE</h1>

<h2>When the function is not finished executing  it will remain in stack.</h2>
```
#include <stdio.h>
int main()
{
 print1();
}
print1()
{
 printf("1")
 print2();
}
print2()
{
 printf("2");
 print3();
}
print3()
{
printf("3");
} 

```

STACK
<html>
<script>alert()</script>
</html>
---
![[recursion.excalidraw]]


---


<h3> When a function finishes executing it is removed from stack and the flow of program is restored where the function is called. </h3>

<p> Base Condition in Recursion </p>
-> Condition where our recursion will stop making new calls.
```
int main()
{
print1(1);
}
print1(int n)
{
  printf("%d",n);
  print1(n+1);
}
```
<i> here in this code code running for infinity time, so we need <b>base condition</b> to stop  </i>
```
int main()
{
print1(1);
}
print1(int n)
{
  if(n==5) // base condition
  {
  return;
  }
  printf("%d",n);
  print1(n+1);
}

```
<p> NO base condition -> function calls will keep happening , stack will be filled again and again and every calls of function take memory, and one time memory of computer exceeds the limit and -> gives <b> Stack Overflow error </b> </p>
-> The base condition is represented by answers we already have. For example , in Fibonacci number, we know that f(0) = 0 and f(1) = 1 . So this is base condition.

<p>Recursion:- </p>  Recursion is function calling itself.
<p>Why Recursion</p>
--> It helps us in solving bigger/complex problems in a simple way. 
--> We can convert recursion solution into iteration and vice versa. because directly solving into iteration is difficult. so, we use recursion. (iteration means for and while loop)
--> Space Complexity is not constant because of recursive calls.

<p>Recurrence Relations</p>
-> When we write the recursion in formula is called recurrence relations.

<p> Tail Recursion </p>
Tail recursion is a specific type of recursion in computer programming where a function/recursive  calls itself as its last action before returning a value.
like `return print1(n+1)` and this is not tail recursion `return fib(n-1) + fib(n-2)` because for `fib(n) to be called first fib(n-1)+fib(n-2) must calculated so.`