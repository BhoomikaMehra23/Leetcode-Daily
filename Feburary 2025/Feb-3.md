# 📌 LeetCode Daily - 3rd February 2025  

## 🔹 Problem: **Longest Strictly Increasing or Strictly Decreasing Subarray**  
You are given an array of integers `nums`. Return the length of the **longest subarray** of `nums` which is either **strictly increasing** or **strictly decreasing**.  

### **🔹 Problem Explanation**  
- A **strictly increasing subarray** means each element is **greater** than the previous one.
- A **strictly decreasing subarray** means each element is **less** than the previous one.
- The goal is to find the **maximum** length of such a subarray.

### **🔹 Examples**  

#### Example 1:  
Input: nums = [1,4,3,3,2] Output: 2

Explanation: The strictly increasing subarrays are: [1], [2], [3], [3], [4], [1,4]. The strictly decreasing subarrays are: [1], [2], [3], [3], [4], [3,2], [4,3]. The longest has length 2.

#### Example 2:  
Input: nums = [3,3,3,3] Output: 1

Explanation: The strictly increasing subarrays are: [3], [3], [3], [3]. The strictly decreasing subarrays are: [3], [3], [3], [3]. The longest has length 1.

#### Example 3:
Input: nums = [3,2,1] Output: 3

Explanation: The strictly increasing subarrays are: [3], [2], [1]. The strictly decreasing subarrays are: [3], [2], [1], [3,2], [2,1], [3,2,1]. The longest has length 3.


### **🔹 Constraints**  
- `1 <= nums.length <= 50`
- `1 <= nums[i] <= 50`

---

## **🔹 Solution Approach**  

### **🔹 Approach: Two Pointers for Monotonic Sequences**  
- **Initialize two counters:**  
  - `incLen = 1` (length of the increasing sequence)  
  - `decLen = 1` (length of the decreasing sequence)  
  - `maxLen = 1` (tracks the maximum of both)  
- **Traverse the array and compare adjacent elements:**  
  - If `nums[i] > nums[i-1]`: Increase `incLen`, reset `decLen` to `1`.
  - If `nums[i] < nums[i-1]`: Increase `decLen`, reset `incLen` to `1`.
  - If `nums[i] == nums[i-1]`: Reset both to `1`.
  - Keep updating `maxLen` with the highest value found.

### **🔹 Code Implementation (Java)**  
```java
class Solution {
    public int longestMonotonicSubarray(int[] nums) {
        int maxLen = 1;
        int incLen = 1, decLen = 1;
        
        for (int i = 1; i < nums.length; i++) {
            if (nums[i] > nums[i - 1]) {
                incLen++;
                decLen = 1;
            } else if (nums[i] < nums[i - 1]) {
                decLen++;
                incLen = 1;
            } else {
                incLen = 1;
                decLen = 1;
            }
            maxLen = Math.max(maxLen, Math.max(incLen, decLen));
        }
        
        return maxLen;
    }
}

🔹 Time & Space Complexity
Time Complexity: O(N), as we iterate through the array once.
Space Complexity: O(1), as we use only a few variables.

🔹 Summary
✅ Identified increasing and decreasing subarrays.
✅ Implemented an efficient Java solution with O(N) time complexity.
✅ Covered edge cases like duplicates and single-element arrays.

🌟 Keep Solving & Stay Consistent! 🚀



