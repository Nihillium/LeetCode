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
[Array](https://leetcode.com/tag/array/), [Hash Table](https://leetcode.com/tag/hash-table/), [Sorting](https://leetcode.com/tag/sorting/)

**Similar Questions**:
* [Contains Duplicate II (Easy)](https://leetcode.com/problems/contains-duplicate-ii/)
* [Contains Duplicate III (Hard)](https://leetcode.com/problems/contains-duplicate-iii/)
* [Make Array Zero by Subtracting Equal Amounts (Easy)](https://leetcode.com/problems/make-array-zero-by-subtracting-equal-amounts/)

## Solution 1.
<pre>
<strong>Time  :</strong> O(n)
<strong>Space :</strong> O(n)
</pre>
```cpp
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
<pre>
<strong>Time  :</strong> O(n log n)
<strong>Space :</strong> O(1)
</pre>
```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        for (int i = 0; i < nums.size() - 1; i ++) {
            if (nums[i] == nums[i + 1]) {
                return true;
            }
        }
        return false;
    }
};
```
