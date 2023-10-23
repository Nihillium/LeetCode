# [217. Contains Duplicate (Easy)](https://leetcode.com/problems/contains-duplicate/)

<p>Given an integer array <code>nums</code>, return <code>true</code> if any value appears <strong>at least twice</strong> in the array, and return <code>false</code> if every element is distinct.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<pre><strong>Input:</strong> nums = [1,2,3,1]
<strong>Output:</strong> true
</pre><p><strong>Example 2:</strong></p>
<pre><strong>Input:</strong> nums = [1,2,3,4]
<strong>Output:</strong> false
</pre><p><strong>Example 3:</strong></p>
<pre><strong>Input:</strong> nums = [1,1,1,3,3,4,3,2,4,2]
<strong>Output:</strong> true
</pre>
<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10<sup>5</sup></code></li>
	<li><code>-10<sup>9</sup> &lt;= nums[i] &lt;= 10<sup>9</sup></code></li>
</ul>


**Companies**:  
[Apple](https://leetcode.com/company/apple), [Amazon](https://leetcode.com/company/amazon), [Adobe](https://leetcode.com/company/adobe), [Microsoft](https://leetcode.com/company/microsoft)

**Related Topics**:  
[Array](https://leetcode.com/tag/array/), [Hash Table](https://leetcode.com/tag/hash-table/)

**Similar Questions**:
* [Contains Duplicate II (Easy)](https://leetcode.com/problems/contains-duplicate-ii/)
* [Contains Duplicate III (Medium)](https://leetcode.com/problems/contains-duplicate-iii/)

## Solution 1.
**Intuition**: To check for duplicate values in an integer array, we can use an unordered set (`st`) to keep track of unique values as we iterate through the array. If we encounter a value that is already in the set, it means there's a duplicate, and we return `true`. If we complete the iteration without finding any duplicates, we return `false`.

**Algorithm**:
1. Initialize an unordered set `st` to keep track of unique values.
2. Iterate through each element `num` in the input vector `nums`.
3. For each `num`, check if it's already in the `st` set using `st.count(num)`.
4. If `num` is found in the set (i.e., `st.count(num)` is greater than 0), return `true`. This indicates the presence of a duplicate in the array.
5. If `num` is not found in the set, insert it into the `st` set using `st.insert(num)`. This keeps track of unique elements encountered so far.
6. After completing the loop without returning `true`, return `false`. This indicates that there are no duplicate elements in the array.
```cpp
// OJ: https://leetcode.com/problems/contains-duplicate/
// Author: github.com/lzl124631x
// Time: O(N)
// Space: O(N)
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set <int> st;
        for (const auto &num : nums) {
            if (st.count(num)) return true;
            else st.insert(num);
        }
        return false;
    }
};
```


## Solution 2.

```cpp
// OJ: https://leetcode.com/problems/contains-duplicate/
// Author: github.com/lzl124631x
// Time: O(NlogN)
// Space: O(1)
class Solution {
public:
    bool containsDuplicate(vector<int>& A) {
        sort(begin(A), end(A));
        for (int i = 1; i < A.size(); ++i) {
            if (A[i] == A[i - 1]) return true;
        }
        return false;
    }
};
```
