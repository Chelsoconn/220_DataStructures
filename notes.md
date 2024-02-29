**Big O Notation**

"O" stands for order. Refers to the order of magnitude of the algorithm's growth rate.  In simple terms, it's about understanding which part of the algorithm has the most significant impact on how its run time increases with larger inputs.

Big O is called "Big" because it's concerned with the biggest factor that affects an algorithm's time complexity. It ignores less significant terms and constants that don't significantly change the overall trend as the input size gets very large.

*Worst-Case Scenario*

With Big O Notation, we describe the upper limit or **the worst-case scenario** of an algorithm's time complexity. The worst-case scenario is the situation where the algorithm takes the longest possible time to complete a task.  In Big O, we often focus on the worst-case because it gives us a limit for how long the algorithm could take. It tells us about the maximum time complexity we can expect, no matter what specific data we feed into the algorithm.

*Linear Search Worst-Case*

For linear search, the worst-case happens when the element we're looking for is either the last one in the list or not there at all. In these cases, the algorithm has to check every single element. That's why linear search has a time complexity of `O(N)`, pronounced `"oh of N"`, where `N` is the input size.

**Time Complexity**

 How the algorithm's performance scales with the size of the input, or, in other words.  Big O Notation allows us to focus on the scalability of an algorithm, enabling us to compare and analyze different algorithms more effectively. Instead of focusing on the exact number of steps, we shift our attention to the growth rate of the algorithm as the input size increases.

**Time Complexities from Constant to Factorial**

*O(1)*

Number of steps required to complete an operation stays the same, regardless of size of input.  This constancy means that the operation does not become slower as the input size increases. It's important to note that `O(1)` doesn't imply the operation takes only one step; it means the number of steps doesn't vary with input size.

​	*example*

A classic example of an `O(1)` operation is retrieving a value from a hash table, such as an object in JavaScript. In a hash table, data is organized in key-value pairs. Accessing a value using its key is a constant-time operation because it doesn't matter how large the hash table is or how many elements it contains; finding a value by its key always takes the same amount of time. This efficiency is due to the hash function, which computes an index for where the value is stored, thus allowing direct access without needing to search through the entire data structure.

Another example of `O(1)` complexity is accessing an array element by its index. The size of the array does not affect the steps required to access a particular element. This is because arrays have a fixed memory layout, allowing each element's location to be determined directly from its index.



*O(logN)*

When we discuss an algorithm with `O(logN)` time complexity, we are referring to a situation where the number of steps necessary to complete a task increases in proportion to **the logarithm of the input size**. 

A well-known example of `O(logN)` complexity is the binary search algorithm. In binary search, we find a specific value in a sorted array by repeatedly dividing the search space in half. Here's how it works in JavaScript:

```js
function binarySearch(sortedArray, target) {
    let start = 0;
    let end = sortedArray.length - 1;

    while (start <= end) {
        let mid = Math.floor((start + end) / 2);
        if (sortedArray[mid] === target) {
            return mid; // Target found
        } else if (sortedArray[mid] < target) {
            start = mid + 1; // Search right half
        } else {
            end = mid - 1; // Search left half
        }
    }
    return -1; // Target not found
}
```

The logarithmic nature of binary search becomes clear when we consider large arrays. If you have an array of 1,000 elements, a binary search would need about 10 steps in the worst case (as `log2(1000)` is approximately 10). Doubling the array size to 2,000 elements increases the steps needed only by one, to approximately 11 steps. This demonstrates logarithmic growth, where increasing the number of elements significantly doesn't proportionally increase the number of steps required.

To recap, logarithmic algorithms, like binary search, are efficient, especially with large data sets. They considerably reduce the number of steps needed compared to linear (`O(N)`) algorithms, which we will discuss in the upcoming section. Each step in an `O(logN)` algorithm drastically reduces the remaining problem size.



*O(N)*

The `O(N)` time complexity means that the performance of an algorithm or operation is directly proportional to the size of the input, denoted by `N`.  This direct proportionality means that there is a one-to-one relationship between the increase in input size and the corresponding increase in the number of operations or time required. Put simply, if you double the size of the input, the number of steps or the time needed to complete the task also doubles.

ex/ linear search

