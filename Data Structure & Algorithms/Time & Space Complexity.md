<p> What is Time Complexity?</p>
-> Time Complexity != Time Taken
->  Time Complexity is the function that gives us the relationship about how the time will grow as the input grows.

<p> What do we consider when thinking about complexity?</p>
-> Always look for worst case complexity.
-> Always look at complexity for large data.
-> We dont care about actual time.
-> Ignore Constant.
-> Always ignore less dominent values.(O(N^3+log(N))) -> here log(N) is comparitively less that N^3.

<p> Big-Oh Notation</p>

-> Upper Bound
-> O(N^3) say the complexity never exceeds N^3.  But the algorithm have best case as N^2, N^1 etc.
```
lim  f(n)/g(n) < ∞
n->∞
```


<p>Big-Omega Notation </p>
-> Opposite of Big-Oh Notation
-> Ω(N^3) means the algorithm takes at least N^3 complexity. It can takes N^4 or ++ also .
-> Lower Bound
```
lim   f(n)/g(n)  > 0
n->∞

]
```


<p>Big-Theta Notation </p>
-> Combining both Upper Bound and Lower Bound.
```
0 <  lim   f(n)/g(n)  < ∞
     n->∞
```
<p> Little Oh notation </p>
-> This is also giving upper bound.
-> Loose upper bound.
-> example in Big-Oh `f = O(g) means f<= g` but in little Oh `f=O(g) means f<g`

<p> Little Omega</p>
-> In Big Omega `f = Ω(g) means f>=g` but In little Omega `f =Ω(g) means f>g`
Question:-
```
for(i =1; i<=N)
{
  for(j = 1; j<=k; j++)
  {
    //some operation that take time t
  }
  i = i+k;
}

-> for inner loop -> inner loop run k time and does some operation that take time t so -> inner loop time complexity ->  k*t
-> for outer loop -> loop run through 1 , 1+k , 1+2k, 1+3k, 1+4k,...., 1+xk so that 1+xk <=N -> xk <= N-1 -> x = (N-1)/k 

Time Complexity -> O(kt * (N-1)/k) -> O(Nt)
```

<h2> Space Complexity </h2>
-> Space Complexity = Extra space used by algorithm( Auxillary Space) + space used by input.


