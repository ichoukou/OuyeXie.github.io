 - [Top 10 Algorithms for Coding Interview](http://www.programcreek.com/2012/11/top-10-algorithms-for-coding-interview/)
    - bookmark 
        - string 
            - 10 20160909
            - 20 20160910
            - 31 20160910
            - 35 20160911
            - 56 20160912
        - matrix
            - 07 20160914
        - linked list
            - 01 20160914
            - 10 20160914
            -> 15 20160914
        - tree
            - 01 20160912
            - 07 20160913
        - bst
            - Lowest Common Ancestor of a Binary Search Tree 
                - [[LeetCode]Lowest Common Ancestor of a Binary Search Tree ](http://blog.csdn.net/xudli/article/details/46871283)
            - Inorder Successor in BST
                - [LeetCode 285 [Inorder Successor in BST]](http://www.jianshu.com/p/218f686d6494)
        - heap
            - 05 20160913
        - trie
            - 02 20160913
        - segment tree
            - 01 20160913
            - the skyline problem
                - [[LeetCode] The Skyline Problem](http://www.cnblogs.com/easonliu/p/4531020.html)
                    - not through yet
        - graph
            - 04 20160913
                - [[LeetCode] Reconstruct Itinerary 重建行程单](http://www.cnblogs.com/grandyang/p/5183210.html)
        - sort
            - 05 20160914
        - dynamic programming
            - 03 20160914
        - bit
            - 02 20160910
            - 04 20160914
        - combination and permutation
        - math
            - 09 20160914
                - [[LeetCode]Factorial Trailing Zeroes ](http://bookshadow.com/weblog/2014/12/30/leetcode-factorial-trailing-zeroes/)
        - hashmap
            - 01 20160914
                - [[Leetcode] Shortest Word Distance 最短单词间距](https://segmentfault.com/a/1190000003906667)
        - additional
            - 01 20160914
                - [[LeetCode] Self Crossing 自交](http://www.cnblogs.com/grandyang/p/5216856.html)
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
        - [几种排序以及其时间复杂度](http://blog.sina.com.cn/s/blog_771849d301010ta0.html)
        - merge sort 
            - [排序七 归并排序](http://www.cnblogs.com/jingmoxukong/p/4308823.html)
                - I am a serie
        - Heap sort
            - [数据结构之“堆”](http://www.cnblogs.com/Jason-Damon/archive/2012/04/18/2454649.html)
                - the best
            - [堆结构的java实现](http://lotusyu.iteye.com/blog/1061822)
            - [Java排序算法（三）：堆排序](http://blog.csdn.net/apei830/article/details/6584645)
            - [堆排序(Heapsort)之Java实现](http://blog.csdn.net/kimylrong/article/details/17150475)
        - Quick sort
            - 设要排序的数组是A[0]……A[N-1]，首先任意选取一个数据（通常选用数组的第一个数）作为关键数据，然后将所有比它小的数都放到它前面，所有比它大的数都放到它后面，这个过程称为一趟快速排序。值得注意的是，快速排序不是一种稳定的排序算法，也就是说，多个相同的值的相对位置也许会在算法结束时产生变动。
        - Bubble Sort
            - 它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。
        - Counting Sort
            - [经典排序算法 - 计数排序Counting sort](http://www.cnblogs.com/kkun/archive/2011/11/23/2260299.html)
            - [计数排序](http://baike.baidu.com/link?url=1djCkq11pAaHA1pXsuYocXmnCkkRjrLtnKKl8-D_M1-wdlwspUT4_vT9JgVfnnYV3eDQXmxWnEOX1dK2hXWFRK)
                - 计数排序是一个非基于比较的排序算法，该算法于1954年由 Harold H. Seward 提出。它的优势在于在对一定范围内的整数排序时，它的复杂度为Ο(n+k)（其中k是整数的范围），快于任何比较排序算法。[1-2]  当然这是一种牺牲空间换取时间的做法，而且当O(k)>O(n*log(n))的时候其效率反而不如基于比较的排序（基于比较的排序的时间复杂度在理论上的下限是O(n*log(n)), 如归并排序，堆排序）
            
     - kmp
         - [strStr](http://www.programcreek.com/2012/12/leetcode-implement-strstr-java/)
             - [KMP](http://jakeboxer.com/blog/2009/12/13/the-knuth-morris-pratt-algorithm-in-my-own-words/) not checked yet
             
     - Moores's Voting algorithm
        - [A Linear Time Majority Vote Algorithm](http://www.cs.utexas.edu/~moore/best-ideas/mjrty/)
        
     - Pascal's triangle
        - 第n行m列元素应该为：C(n-1,m-1)=(n-1)!/[(m-1)!(n-m)!]
        
     - Tree
        - [图解数据结构（6）——树及树的遍历](http://www.cnblogs.com/yc_sunniwell/archive/2010/06/27/1766233.html)
        - [三种遍历树的算法](http://blog.csdn.net/presidentpresident/article/details/7549170)
        - [数据结构：关于重建二叉树的三种思路](http://blog.csdn.net/lemon_tree12138/article/details/49798221)
        - [Serialization/Deserialization of a Binary Tree](http://blog.csdn.net/wolenski/article/details/7938461)
        - [重建二叉树](http://blog.csdn.net/shanshanpt/article/details/8685608)
        - [编程之美--重建二叉树](http://blog.csdn.net/luyafei_89430/article/details/12967411)
            - detail
     - binary search tree
        - The tree additionally satisfies the binary search tree property, which states that the key in each node must be greater than all keys stored in the left sub-tree, and smaller than all keys in the right sub-tree.
        - 若它的左子树不空，则左子树上所有结点的值均小于它的根结点的值； 若它的右子树不空，则右子树上所有结点的值均大于它的根结点的值
        - Binary Search Tree: for all nodes, left children <= current node <= right children
          Balanced vs. Unbalanced: In a balanced tree, the depth of the left and right subtrees of every node differ by 1 or less.
        - [【基础知识】 之 Binary Search Tree 二叉搜索树](http://www.cnblogs.com/elaron/archive/2013/04/11/3015155.html)
            - 为了降低二叉搜索树的高度而提出了平衡二叉树（Balanced Binary Tree）的概念。它要求左右两个子树的高度差的绝对值不超过1，并且左右两个子树都是一棵平衡二叉树。这样就可以将搜索树的高度尽量减小。常用算法有红黑树、AVL、Treap、伸展树等
        - [数据结构-BST(Binary Search Tree)](http://blog.csdn.net/jarily/article/details/8679280)
     - Bit 
        - OR (|)	AND (&)	XOR (^)	Left Shift (<<)	Right Shift (>>)	Not (~)