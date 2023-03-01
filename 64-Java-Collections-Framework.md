# Java Collections Framework

## Limitations of Array:

1. Static Size - Once an array is created, you cannot add or remove elements from it (easily) during the program runtime.
1. Deletion and insertion at a given position in array - requires the elements to be shifted - and to accomplish this task requires a complete algorithm that the programmer has to code manually. 
1. Sorting and Searching - Need to explicitly write the required algorithms everytime.
1. Prone to memory wastage - If there are less number of elements involved than the specified array size.

All the limitations faced by an Array data structure - with the usage and manipulation of collection data - are addressed by the **Collection Framework**.

## Collection Framework

It is a framework that provides an API to - represent and manipulate a collection of objects efficiently. 

![](imgfiles\chap64\Collection.png)

## Collection Framework : Interfaces

1. **Collection** - the root of collection hierarchy, represents a collection of objects called elements.
1. **List** - an ordered collection, can have duplicate values, can control where in the list an element is positioned, an element can be accessed based on their position (index)
1. **Set** - a collection that cannot have duplicate elements.
1. **Map** - contains key-vallue pairs, cannot have duplicate keys, each key can map to atmost one value, key can be used foer accessing the value

![](imgfiles\chap64\2023-02-22-21-32-37.png)


## Collection Framework : Common Methods 

![](imgfiles\chap64\2023-02-22-21-35-50.png)

![](imgfiles\chap64\2023-02-22-21-39-34.png) &nbsp;&nbsp;&nbsp;&nbsp; ![](imgfiles\chap64\2023-02-22-21-41-03.png)

![](imgfiles\chap64\2023-02-22-21-43-31.png) &nbsp;&nbsp;&nbsp;&nbsp; ![](imgfiles\chap64\2023-02-22-21-44-37.png)

![](imgfiles\chap64\2023-02-22-21-47-15.png) &nbsp;&nbsp;&nbsp;&nbsp; ![](imgfiles\chap64\2023-02-22-21-49-49.png)

![](imgfiles\chap64\2023-02-22-21-51-31.png) &nbsp;&nbsp;&nbsp;&nbsp; ![](imgfiles\chap64\2023-02-22-21-52-43.png)

![](imgfiles\chap64\2023-02-22-21-54-50.png) &nbsp;&nbsp;&nbsp;&nbsp; ![](imgfiles\chap64\2023-02-22-21-55-31.png)