## Iterative Algorithm Analysis

Hello there! This document is a tutorial on how to analyze the time complexity of iterative algorithms.

For this tutorial, we will be analyzing the following algorithm, written in pseudocode:

```pseudocode
ALGORITHM CountGreaterThanFirst(Array):
	// This algorithm counts the number of elements in a given array that are greater 
	// than the first element
	// input: Array is an array of integers
	// output: an integer representing the number of elements that are greater than the
	// first element in the array
	let firstElement = A[0]
	let numGreater = 0;
	for i <- 1; i < |Array|; i++:
		if A[i] > firstElement:
			numGreater++
		end
	end
	return numGreater
```

Alright, let's jump right in!

### Step 1: Decide on a Parameter (or Parameters) Indicating the Algorithm's Input's Size

For this step, you'll want to choose the aspect of the input that most greatly affects how long the algorithm will run. This parameter is often represented as *n*. When your input is an array, n is almost always the size of the array. However, it could other things in other cases. For example, if an algorithm counts down from an integer that's inputted, instead the size would be the integer itself.

For our example, n is the size of the array inputted, as this most clearly affects how long the algorithm will run.

### Step 2: Identify the Algorithm’s Basic Operation

For this step, you'll want to identify the part of the algorithm that contributes the most to the total running time. It's generally the line of code that does the core "work" of the algorithm. This will allow for us to put how long the algorithm runs in terms of the basic operation rather than time or clock cycles, as those could vary even for the same input. 

For our example, the basic operation is the comparison between each element of the array and the first element. This is because it contributes the most to the run time of the algorithm and does the core "work" of finding elements that are greater than the first element.

### Step 3: Check For Other Dependencies

For this step, you'll want to see if there's anything else about the input that could change how long the algorithm will run. For example, if you're analyzing an algorithm that checks every element in an array in order until it finds one that matches a certain value, then the algorithm would obviously run significantly faster if the value it's looking for happens to be the first one in the array. In these cases, you'll have to split your analysis into 3 cases: best case, average case, and worst case. For the searching algorithm, the best case is if the first element is what you're looking for, the average case is that the element is somewhere in the middle of the array, and the worst case is if the element isn't in the array or is the last element.

For our example, the basic operation has no other dependencies, as no matter what the elements are in the array, every other element will have to be compared to the first element.

### Step 4: Set Up a Summation

For this step, you'll set up a summation to represent the number of basic operations that occur for a given n. This summation should represent how many basic operations occur in terms of n. You'll want to start from the innermost loop, if there are any, then find out how many basic operations happen in that loop, then find out how many times that loop occurs, and so on.

For our example, a basic operation will occur once every time it goes through the loop. This loop will occur n-1 times, where n is the parameter we defined earlier as the size of the array. In this case, the array is simple enough to be represented just as *n*, but if you insist on using a summation, it can be represented as such: 
$$
\sum_{i=1}^{n}1
$$


### Step 5: Create a Formula

For this step, you would take the summation you created, then simplify it to a function of n rather than there being two variables, i and n. This can be done by using the below summation formulas and rules.

![](https://www.cheatography.com/uploads/cddc_1456260490_image[8].png)

![](https://www.cheatography.com/uploads/cddc_1456260571_clip_image004[5].png)

(Images taken from  https://www.cheatography.com/cddc/cheat-sheets/cpsc221mt/)

In our example, we can simplify the summation we created to see that it really is equal to n using formula 1.

And there you are! That is how you analyze the time complexity of an iterative algorithm.

Shield: [![CC BY-SA 4.0](https://camo.githubusercontent.com/6dcc300ab83c479af6c1c1f004b6f9dad77e7736/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c6963656e73652d434325323042592d2d5341253230342e302d6c69676874677265792e737667)](http://creativecommons.org/licenses/by-sa/4.0/)

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

[![CC BY-SA 4.0](https://camo.githubusercontent.com/68525ec5f8acf359e826761fa50e9262da143eb5/68747470733a2f2f6c6963656e7365627574746f6e732e6e65742f6c2f62792d73612f342e302f38387833312e706e67)](http://creativecommons.org/licenses/by-sa/4.0/)