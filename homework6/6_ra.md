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
Similar to balancing BST in, we can use a max heap to represent elements that are less than effective median, and a min-heap to represent elements that are greater than effective median. \
The steps to follow to implement this method are the following: \
**Step 1:** Add the new value of the stream to the max heap.\
**Step 2:** Remove the top of max heap and add it to the min heap.\
**Step 3:** If the max heap size is less than min heap than remove the top of min heap and add it to the max heap.\
**Step 4:** For finding the median: if the size of max heap is greater than min heap then peek the top of max heap. If both max heap and min heap are same size than peek the top of max heap and min heap, add both and divide it by 2.\
Time Complexity to insert element in a heap is logn. So to insert n element is O(n*logn). This one is the most efficient between the three methods presented.

Let's see now an implementation for computing the running median using two heaps.

{% highlight C# %}
class RunningMedian
{
    MaxHeap<double> max_heap;
    MinHeap<double> min_heap;

    public RunningMedian(){
        max_heap = new MaxHeap<double>();
        min_heap = new MinHeap<double>();
    }

    public void AddValue(double value)
    {
        max_heap.Add(value);
        min_heap.Add(max_heap.ExtractMax());
        if (max_heap.Count < min_heap.Count) max_heap.Add(min_heap.ExtractMin());
    }

    public double GetMedian()
    {
        if (max_heap.Count > min_heap.Count) return max_heap.GetMax();
        else
        {
            double max = max_heap.GetMax();
            double min = min_heap.GetMin();

            return (min + max) / 2;
        }
    }
}
{% endhighlight %}

To make this solution the max heap and min heap implementation have been got by [this GitHub page](https://github.com/JetStream96/MinMaxHeap) while the RunningMedian class has been made by the writer of this article.
    
A little demo can be seen in the next video and can be downloaded [pressing this link](https://drive.google.com/file/d/12AgS-Jhun2Ae9FmaFn6VUB2UAFsQkG6_/view?usp=sharing).
    
The video of the whole application can be found below.
<iframe src="https://user-images.githubusercontent.com/78324346/139830359-c3cc52e0-1944-4c6b-831f-8e089d1ef29c.mp4" width="700" height="480" frameborder="0" allowfullscreen=""> </iframe>

[1][https://www.geeksforgeeks.org/median-of-stream-of-integers-running-integers/](https://www.geeksforgeeks.org/median-of-stream-of-integers-running-integers) \
[2][https://en.wikipedia.org/wiki/Median](https://en.wikipedia.org/wiki/Median) \
[3][https://www.youtube.com/watch?v=EIm2n8iPA4I&t=174s](https://www.youtube.com/watch?v=EIm2n8iPA4I&t=174s)
