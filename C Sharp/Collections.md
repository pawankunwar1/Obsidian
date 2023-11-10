 -> A Collection is a set of related data that may not necessarily belong to the same data type that can be set or modified dynamically at run-time.
In other words, collection is a dynamic array i.e its length can increase on runtime(auto resizing). Normal Arrays length is fixed, it means we cannot change the length after declaring an array.

->Resize method of an array destroys old array and create a new array with new length. We can never insert a value into a middle of an array, because if we want to do this then array length should be increased but we cannot increase the length of an array after declaring the length of an array. We can never delete a value from a middle of array. Accessing collections is similar to accessing arrays, where elements are accessed by their index numbers.

Arrays                                                                                                            Collection
1) Cannot be resized at run-time.                                               1) Can be resized at run-time
2)The individual elements are of the same data type                 2)The individual elements         can be of different data types.
3)Do not contain any methods for operations on elements    3) Contains methods for operation on elements
4)We can never insert a value into a middle of an array         4) We can insert a value into a middle of collection
5) We can never delete a value from a middle of an array   5)We can delete a value from a middle of a collection.

<b>Two Types Collections </b>
1) Non-Generic Collections -> Stack, ArrayList, Hashtable, SortedList etc. -> System.collections namespace have non-generic collections
2) Generic Collections -> List<T> , LinkedList<T> , Queue<T>, SortedList<T, V> --> System.Collections.Generic namespace have generic collections.

In Array and ArrayList data are stored in key/value format but keys are pre-defined i.e index numbers, it means we cannot explicitly define keys in Array or ArrayList.

 In HashTable, keys are not pre-definde it means we can explictly define user-defined keys in HashTable. 
 
Hashtable ht = new Hashtable();
ht.Add(key, value);

Hashtable ht = new Hashtable(){
{"id",1123}}   --> We cannot store duplicate value here i.e duplicate keys


->Array -> Type Safe(means same type of data stored) -> Fixed Length
->Non-Generic -> Not Type safe(means can store different type of data types) -> Not fixed Length
-> Generic -> Type safe and not fixed length(auto resizing)


Generic is better than non generic because Generic give compile time error but non-generic error give run-time error.
```
example
class Generic

{
static void Main(string[] args)
{
ArrayList ages1 = new ArrayList();

ages1.Add(12);

ages1.Add("hello");

int value = (int)ages1[1]; -. it gives error at run-time
List<int> ages = new List<int>();

ages.Add(12);

//ages.Add("hello");

System.Console.WriteLine();

System.Console.WriteLine("hello");

  
  

}

  

}
```



