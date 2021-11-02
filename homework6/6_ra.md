**Made by Nicolò Baroncini (1834907)**

## Research about application(6_RA)
### Do a web research about the various methods proposed to compute the running median (one pass, online algorithms). Store (cite all sources and attributions) the algorithm(s) that you think is(are) a good candidate, explaining briefly how it works and possibly try a quick demo.
First of all let's see what is the median. \
A median of a population is any value such that at most half of the population is less than the proposed median and at most half is greater than the proposed median.\
An explanatory image is the following.

![image](https://user-images.githubusercontent.com/78324346/139809043-99c006fc-36d1-4df2-9161-e648ff1a7b93.png)

To compute the median in a stream of numbers there are some different methods.

**Using insertion sort**
If we can sort the data as it appears, we can easily locate the median element. Insertion Sort is one such online algorithm that sorts the data appeared so far. At any instance of sorting, say after sorting i-th element, the first i elements of the array are sorted. The insertion sort doesn’t depend on future data to sort data input till that point. In other words, insertion sort considers data sorted so far while inserting the next element. This is the key part of insertion sort that makes it an online algorithm. However, insertion sort takes O(n²) time to sort n elements. After the data is ordered we can locate the median as the value in the center of the ordered array.

**Implementation with self balanced Binary Search Tree (BST)**
At every node of BST, maintain a number of elements in the subtree rooted at that node. We can use a node as the root of a simple binary tree, whose left child is self-balancing BST with elements less than root and right child is self-balancing BST with elements greater than root. The root element always holds effective median.
If the left and right subtrees contain a same number of elements, the root node holds the average of left and right subtree root data. Otherwise, the root contains the same data as the root of subtree which is having more elements. After processing an incoming element, the left and right subtrees (BST) are differed utmost by 1.
Self-balancing BST is costly in managing the balancing factor of BST. However, they provide sorted data which we don’t need. We need median only.

[1][https://www.geeksforgeeks.org/median-of-stream-of-integers-running-integers/](https://www.geeksforgeeks.org/median-of-stream-of-integers-running-integers) \
[2][https://en.wikipedia.org/wiki/Median](https://en.wikipedia.org/wiki/Median)
