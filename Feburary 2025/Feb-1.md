# 📌 LeetCode Daily - 1st February 2025  

## 🔹 Problem: **3151. Special Array I**  
An array is considered **special** if every pair of its adjacent elements contains numbers with **different parity** (one even, one odd).  

### **🔹 Problem Statement**  
You are given an array of integers `nums`. Return **true** if `nums` is a special array, otherwise, return **false**.  

### **🔹 Examples**  

#### Example 1:  
```
Input: nums = [1]  
Output: true  
Explanation: There is only one element. So the answer is true.
```

#### Example 2:  
```
Input: nums = [2,1,4]  
Output: true  
Explanation: Pairs (2,1) and (1,4) both have different parity.
```

#### Example 3:  
```
Input: nums = [4,3,1,6]  
Output: false  
Explanation: nums[1] and nums[2] are both odd, so the answer is false.
```

### **🔹 Constraints**  
- `1 <= nums.length <= 100`  
- `1 <= nums[i] <= 100`  

---

## **🔹 Solution Approach**  

### **🔹 Approach 1: Iteration (Brute Force)**  
- Check every adjacent pair `nums[i]` and `nums[i+1]`.  
- If both are **even** or **odd**, return **false**.  
- If no such case is found, return **true**.  


### **🔹 Code Implementation (Java)**  
```java
class Solution {
    public boolean isSpecialArray(int[] nums) {
        for (int i = 0; i < nums.length - 1; i++) {
            if ((nums[i] % 2) == (nums[i + 1] % 2)) { // Both even or both odd
                return false;
            }
        }
        return true;
    }
    
    public static void main(String[] args) {
        Solution solution = new Solution();
        System.out.println(solution.isSpecialArray(new int[]{1})); // true
        System.out.println(solution.isSpecialArray(new int[]{2, 1, 4})); // true
        System.out.println(solution.isSpecialArray(new int[]{4, 3, 1, 6})); // false
    }
}
```

### **🔹 Time & Space Complexity**  
- **Time Complexity:** `O(N)`, where `N` is the size of `nums`. We check all adjacent pairs once.  
- **Space Complexity:** `O(1)`, as no extra space is used.  
---

### **🌟 Keep Solving & Stay Consistent! 🚀**
