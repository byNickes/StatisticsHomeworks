**Made by Nicolò Baroncini (1834907)**

## Research about application(6_RA)
### Do a web research about the various methods proposed to compute the running median (one pass, online algorithms). Store (cite all sources and attributions) the algorithm(s) that you think is(are) a good candidate, explaining briefly how it works and possibly try a quick demo.
First of all let's see what is the median. \
A median of a population is any value such that at most half of the population is less than the proposed median and at most half is greater than the proposed median.\
An explanatory image is the following.

![image](https://user-images.githubusercontent.com/78324346/139809043-99c006fc-36d1-4df2-9161-e648ff1a7b93.png)

To compute the median in a stream of numbers there are some different methods.

**Method using insertion sort** \
If we can sort the data as it appears, we can easily locate the median element. Insertion Sort is one such online algorithm that sorts the data appeared so far. At any instance of sorting, say after sorting i-th element, the first i elements of the array are sorted. The insertion sort doesn’t depend on future data to sort data input till that point. In other words, insertion sort considers data sorted so far while inserting the next element. This is the key part of insertion sort that makes it an online algorithm. However, insertion sort takes O(n²) time to sort n elements. After the data is ordered we can locate the median as the value in the center of the ordered array.

**Method using self balanced Binary Search Tree (BST)** \
At every node of BST, maintain a number of elements in the subtree rooted at that node. We can use a node as the root of a simple binary tree, whose left child is self-balancing BST with elements less than root and right child is self-balancing BST with elements greater than root. The root element always holds effective median.
If the left and right subtrees contain same number of elements, the root node holds the average of left and right subtree root data. Otherwise, the root contains the same data as the root of subtree which is having more elements. After processing an incoming element, the left and right subtrees (BST) are differed utmost by 1.
Self-balancing BST is costly in managing the balancing factor of BST. However, they provide sorted data which we don’t need. We need median only.

**Method using two Heaps** \
Similar to balancing BST in, we can use a max heap on the left side to represent elements that are less than effective median, and a min-heap on the right side to represent elements that are greater than effective median.
After processing an incoming element, the number of elements in heaps differs utmost by 1 element. When both heaps contain the same number of elements, we pick the average of heaps root data as effective median. When the heaps are not balanced, we select effective median from the root of the heap containing more elements. \
Time Complexity to insert element in a heap is logn. So to insert n element is O(n*logn). This one is the most efficient between the three methods presented.

Let's see now an implementation for computing the running median using two heaps.

{% highlight Java %}
    public double findMedianSortedArrays(int input1[], int input2[]) {
        //if input1 length is greater than switch them so that input1 is smaller than input2.
        if (input1.length > input2.length) {
            return findMedianSortedArrays(input2, input1);
        }
        int x = input1.length;
        int y = input2.length;

        int low = 0;
        int high = x;
        while (low <= high) {
            int partitionX = (low + high)/2;
            int partitionY = (x + y + 1)/2 - partitionX;

            //if partitionX is 0 it means nothing is there on left side. Use -INF for maxLeftX
            //if partitionX is length of input then there is nothing on right side. Use +INF for minRightX
            int maxLeftX = (partitionX == 0) ? Integer.MIN_VALUE : input1[partitionX - 1];
            int minRightX = (partitionX == x) ? Integer.MAX_VALUE : input1[partitionX];

            int maxLeftY = (partitionY == 0) ? Integer.MIN_VALUE : input2[partitionY - 1];
            int minRightY = (partitionY == y) ? Integer.MAX_VALUE : input2[partitionY];

            if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
                //We have partitioned array at correct place
                // Now get max of left elements and min of right elements to get the median in case of even length combined array size
                // or get max of left for odd length combined array size.
                if ((x + y) % 2 == 0) {
                    return ((double)Math.max(maxLeftX, maxLeftY) + Math.min(minRightX, minRightY))/2;
                } else {
                    return (double)Math.max(maxLeftX, maxLeftY);
                }
            } else if (maxLeftX > minRightY) { //we are too far on right side for partitionX. Go on left side.
                high = partitionX - 1;
            } else { //we are too far on left side for partitionX. Go on right side.
                low = partitionX + 1;
            }
        }

        //Only we we can come here is if input arrays were not sorted. Throw in that scenario.
        throw new IllegalArgumentException();
    }

    public static void main(String[] args) {
        int[] x = {1, 3, 8, 9, 15};
        int[] y = {7, 11, 19, 21, 18, 25};

        MedianOfTwoSortedArrayOfDifferentLength mm = new MedianOfTwoSortedArrayOfDifferentLength();
        mm.findMedianSortedArrays(x, y);
    }
}
{% endhighlight %}



[1][https://www.geeksforgeeks.org/median-of-stream-of-integers-running-integers/](https://www.geeksforgeeks.org/median-of-stream-of-integers-running-integers) \
[2][https://en.wikipedia.org/wiki/Median](https://en.wikipedia.org/wiki/Median) \
[3][https://github.com/mission-peace/interview/blob/master/src/com/interview/binarysearch/MedianOfTwoSortedArrayOfDifferentLength.java](https://github.com/mission-peace/interview/blob/master/src/com/interview/binarysearch/MedianOfTwoSortedArrayOfDifferentLength.java)
