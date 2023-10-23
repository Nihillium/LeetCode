# [242. Valid Anagram (Easy)](https://leetcode.com/problems/valid-anagram/)

<p>Given two strings <em>s</em> and <em>t&nbsp;</em>, write a function to determine if <em>t</em> is an anagram of <em>s</em>.</p>

<p><b>Example 1:</b></p>

<pre><b>Input:</b> <em>s</em> = "anagram", <em>t</em> = "nagaram"
<b>Output:</b> true
</pre>

<p><b>Example 2:</b></p>

<pre><b>Input:</b> <em>s</em> = "rat", <em>t</em> = "car"
<b>Output: </b>false
</pre>

<p><strong>Note:</strong><br>
You may assume the string contains only lowercase alphabets.</p>

<p><strong>Follow up:</strong><br>
What if the inputs contain unicode characters? How would you adapt your solution to such case?</p>


**Related Topics**:  
[Hash Table](https://leetcode.com/tag/hash-table/), [Sort](https://leetcode.com/tag/sort/), [String](https://leetcode.com/tag/string/)

**Similar Questions**:
* [Group Anagrams (Medium)](https://leetcode.com/problems/group-anagrams/)
* [Palindrome Permutation (Easy)](https://leetcode.com/problems/palindrome-permutation/)
* [Find All Anagrams in a String (Medium)](https://leetcode.com/problems/find-all-anagrams-in-a-string/)
* [Find Resultant Array After Removing Anagrams (Easy)](https://leetcode.com/problems/find-resultant-array-after-removing-anagrams/)

## Solution 1.
<pre>
<strong>Time  :</strong> O(n)
<strong>Space :</strong> O(u)
<strong>u = Unicode Character Set </strong>
</pre>

```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        if (s.size() != t.size()) return false;
        unordered_map<char, int> counts;
        for (int i = 0; i < s.size(); i++) {
            counts[s[i]]++;
            counts[t[i]]--;
        }
        for (const auto& c : counts) {
            if (c.second != 0) return false;
        }
        return true;
    }
};

```
