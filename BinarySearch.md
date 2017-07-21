# 二分查找(二分搜索)

### 算法思想：

- __whenAndWhere__：当数据量很大适宜采用该算法。<br>
- __condition__：采用二分法查找时，数据需是排好序的。<br>
- __howToRealize__：二分查找算法先比较位于集合中间位置的元素与键的大小，有三种情况（假设集合是从小到大排列的）：
1. 键小于中间位置的元素，则匹配元素必在左边（如果有的话），于是对左边的区域应用二分搜索。<br>
2. 键等于中间位置的元素，所以元素找到。<br>
3. 键大于中间位置的元素，则匹配元素必在右边（如果有的话），于是对右边的区域应用二分搜索<br>
另外，当集合为空，则代表找不到。

### 时间复杂度：

1.最坏情况查找最后一个元素（或者第一个元素）Master定理T(n)=T(n/2)+O(1)所以T(n)=O(log2n)<br>
2.最好情况查找中间元素O(1)查找的元素即为中间元素（奇数长度数列的正中间，偶数长度数列的中间靠左的元素）<br>

### 代码实现：

```java
 public static int binary(int[] array, int value)
    {
        int low = 0;
        int high = array.length - 1;
        while(low <= high)
        {
            int middle = (low + high) / 2;
            if(value == array[middle])
            {
                return middle;
            }
            if(value > array[middle])
            {
                low = middle + 1;
            }
            if(value < array[middle])
            {
                high = middle - 1;
            }
        }
        return -1;
    }
```
