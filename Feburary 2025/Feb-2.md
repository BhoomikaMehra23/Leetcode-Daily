# 📌 LeetCode Daily - 2nd February 2025  

## 🔹 Problem: **Check if Array is Sorted and Rotated**  
Given an array `nums`, return **true** if the array was originally sorted in **non-decreasing order**, then rotated some number of positions (including zero). Otherwise, return **false**.

There may be **duplicates** in the original array.

### **🔹 Problem Explanation**  
A rotated array is formed by taking a **sorted array** and shifting it **left** or **right** by some positions. If `A` is a sorted array, then a rotated version `B` satisfies:

`A[i] == B[(i + x) % A.length]`

where `x` is the rotation count and `%` is the modulo operation.

### **🔹 Examples**  

#### Example 1:  
```
Input: nums = [3,4,5,1,2]
Output: true
Explanation: [1,2,3,4,5] is the original sorted array.
Rotated by x = 3 positions results in [3,4,5,1,2].
```

#### Example 2:  
```
Input: nums = [2,1,3,4]
Output: false
Explanation: No sorted array can be rotated to get nums.
```

#### Example 3:  
```
Input: nums = [1,2,3]
Output: true
Explanation: No rotation needed, as it is already sorted.
```

### **🔹 Constraints**  
- `1 <= nums.length <= 100`
- `1 <= nums[i] <= 100`

---

## **🔹 Solution Approach**  

### **🔹 Approach: Count Breakpoints**  
- A valid rotated sorted array should have **at most one breakpoint** where `nums[i] > nums[i + 1]`.
- If there is **more than one breakpoint**, return `false`.
- If `nums[n-1] > nums[0]` in a rotated array, ensure there’s only one breakpoint.

### **🔹 Code Implementation (Java)**  
```java
class Solution {
    public boolean check(int[] nums) {
        int count = 0;
        int n = nums.length;
        
        for (int i = 0; i < n; i++) {
            if (nums[i] > nums[(i + 1) % n]) {
                count++;
            }
            if (count > 1) return false;
        }
        return true;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        
        int[] nums1 = {3, 4, 5, 1, 2};
        int[] nums2 = {2, 1, 3, 4};
        int[] nums3 = {1, 2, 3};

        System.out.println(sol.check(nums1)); // true
        System.out.println(sol.check(nums2)); // false
        System.out.println(sol.check(nums3)); // true
    }
}
```

### **🔹 Time & Space Complexity**  
- **Time Complexity:** `O(N)`, as we traverse the array once.
- **Space Complexity:** `O(1)`, as we use only a few variables.

---

## **🔹 Summary**  
- ✅ **Count breakpoints** to determine validity.
- ✅ **Implemented Java solution** with `O(N)` time complexity.
- ✅ **Handles edge cases** (like already sorted arrays and duplicates).

---

### **🌟 Keep Solving & Stay Consistent! 🚀**
