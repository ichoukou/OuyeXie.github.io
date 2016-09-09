 - [Top 10 Algorithms for Coding Interview](http://www.programcreek.com/2012/11/top-10-algorithms-for-coding-interview/)
    - bookmark 
        - string 10 20160909
 - [coding-interview-6.pdf](http://www.programcreek.com/wp-content/uploads/2012/11/coding-interview-6.pdf)
     - [System.arraycopy() V.S. Array.copyOf()](http://www.programcreek.com/2015/03/system-arraycopy-vs-arrays-copyof-in-java/)
        - Arrays.copyOf(T[] original, int newLength)
        - System.arraycopy(Object src, int srcPos, Object dest, int destPos, int length)
        - System.arraycopy(arr, 0, copied, 1, 5);//5 is the length to copy
        - int[] copied = Arrays.copyOf(arr, 10); //10 the the length of the new array
        - The difference is that Arrays.copyOf does not only copy elements, it also creates a new array. System.arrayCopy copies into an existing array.
        
     - Data Structure
        - Stack extents Vector
        - PriorityQueue is a Heap in Java
            
        
     - char
        - int = char + char
        - byte、short、char、int 以上类型的运算结果，都是int类型。
        
     - An anagram is a type of word play, the result of rearranging the letters of a word or phrase to produce a new word or phrase, using all the original letters exactly once; for example, Torchwood can be rearranged into Doctor Who.
     
     - Palindromic
     
     - BFS (breath-first search)
     - DFS
     
     - SORT
        - Heap sort
            - [数据结构之“堆”](http://www.cnblogs.com/Jason-Damon/archive/2012/04/18/2454649.html)
            - [堆结构的java实现](http://lotusyu.iteye.com/blog/1061822)
            - [Java排序算法（三）：堆排序](http://blog.csdn.net/apei830/article/details/6584645)
            - [堆排序(Heapsort)之Java实现](http://blog.csdn.net/kimylrong/article/details/17150475)
        - Quick sort
            - 设要排序的数组是A[0]……A[N-1]，首先任意选取一个数据（通常选用数组的第一个数）作为关键数据，然后将所有比它小的数都放到它前面，所有比它大的数都放到它后面，这个过程称为一趟快速排序。值得注意的是，快速排序不是一种稳定的排序算法，也就是说，多个相同的值的相对位置也许会在算法结束时产生变动。
        - Bubble Sort
            - 它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。