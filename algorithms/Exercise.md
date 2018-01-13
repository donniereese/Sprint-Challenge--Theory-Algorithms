# Analysis of Algorithms

## Exercise I. 
_Give an analysis of the running time with respect to the input size n of each of the following program fragments below:_

a. *Answer: * O(n)
```
a = 0;
while (a < n * n * n) {
    a = a + n * n;
}
```
   ### Analysis:
   The tricky part for me was that you are comparing against n^3, however running you would only complete _n_ cycles. This 
   means that the time grows with n.

   Assuming that _a = 0_ and incrementing _n_, we would see the following outputs:
   * *n = 1;* -- 1
   * *n = 2;* -- 2
   * *n = 3;* -- 3
   * *n = 4;* -- 4
   * ... And so on.

b. *Answer: * Infinity / O(n!)
```
// input array is of length n
i = array.length - 1;
while (array[i] > x && i >= 0)
    i = i/2;
```

   ### Analysis:
   Eliminating extraneous comparions such as `array[i] > x` and assuming that it will always allow the loop to run to the 
   conclusion and _i_ being divided in half each cycle, we would never see the loop end in a finite system. Even accounting 
   for raising _i_ to it's ceiling or flooring it as an assumption would still result in far too many cycles for a 
   reasonable stack.

c. *Answer: * O(n^3)
```
sum = 0;
for (i = 1; i < Math.sqrt(n) / 2; i++)
    for ( j = i; j < 8 + i; j++)
        for (k = j; k < 8 + j; k++)
            sum++;
```

   ### Analysis:
   Once again elimination of modifications to the values is important. _n_ will always be iterated over 3 times and grow in 
   time as _n_ grows. Each `for` loop iterates on the previous value of the for loop, always resulting in exponetial 
   growth in time.

d. *Answer: * Infinity / O(n!)
```
sum = 0;
for (i = 0; i < n; i *= 2)
    for (j = 0; j < n; j++)
        sum++
```

   ### Analysis:
   We're still dealing with exponetial growth, however we're facing a problem as well. An overall issue with the complexity 
   seems to involve our first for loop, where _i_ is initialized to *0* and compared with _n_, but looks as though it will 
   never stop due to *0* never incrementing any higher when multiplied by *2* every iteration.

e. *Answer: * O(n^4)
```
sum = 0;
for (i = 0; i < n; i++)
    for (j = i + 1; j < n; j++)
        for (k = j + 1; k < n; k++)
            for (l = k + 1; l < 10 + k; l++)
                sum++;
```

    ### Analysis:
    With `for` loops, it's always are exponential, but this is even more so. Ignoring the insignificant additions to each 
    level of iteration still leaves us with  with *4* levels to calculate one increment of _sum_;

f. *Answer: * O(2n)
```
bunnyEars = function (bunnies) { // here bunnies === n
    if (bunnies === 0) return 0;
    return 2 + bunnyEars(bunnies-1);
}
```

   ### Analysis:
   This would seem simple enough, assuming each bunny has two ears, however this is a recursive problem. It has a halt 
   condition of _bunnies_ being *0* and _bunnies_ does decrement, so that's swell. Running the algorithm shows that 
   the first guess of double of whatever n would be, seeing as the recursion simply emulates a loop.

g. *Answer: * O(n)
```
search = function (array, arraySize, target) { // here arraySize == n
    if (arraySize > 0) {
        if (array[arraySize-1] === target) return true;
        else return search(Array, arraySize-1, target)
    }
}
```

   ### Analysis:
   This is another recursion, but it also has a good check for a floor case as it iterates downward, so we don't have to 
   worry about it being a runaway exponential growth. This will iterates over each item of the array and not stop until it 
   reaches the bottom in a worste case scenario, which is a good result in my book.


## Exercise II.

a. Given an array *a* of _n_ numbers, design a linear running time algorithm to find the maximum value of `a[j] - a[i]`, 
   where _j_ ≥ _i_.

   ```
   let n = 40;
   const a = new Array(n);
   a.fill(25);
   ```
---
> At this point, class starts.  I am going to upload what I have so far.
---











