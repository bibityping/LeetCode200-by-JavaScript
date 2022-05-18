# Leetcode Solutions - Arrays and Matrices

##### [中文版本](Arrays.md)

---

**Table Of Contents:**

- [Leetcode Solutions - Arrays and Matrices](#leetcode-solutions---arrays-and-matrices) - [中文版本](#中文版本) - [Table Of Contents:](#table-of-contents)
  - [LeetCode Solution - #283 Move Zeroes](#leetcode-solution---283-move-zeroes)
    - [Description](#description)
    - [JavaScript Solution](#javascript-solution)

### LeetCode Solution - #283 Move Zeroes

---

#### Description

Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

Example 1:

```
Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
```

Example 2:

```
Input: nums = [0]
Output: [0]
```

Constraints:

- <code>1 <= nums.length <= 10<sup>4</sup></code>
- <code>-2<sup>31</sup> <= nums[i] <= 2<sup>31</sup> - 1</code>

Follow up: Could you minimize the total number of operations done?

#### JavaScript Solution

---

> 📌 Approach #1: Move all non-zero numbers to the front of the number, and fill in the numbers after the array with zeros.

```javascript
var moveZeroes = function (nums) {
  let nonZeroIndex = 0

  for (let i = 0; i < nums.length; i++) {
    if (nums[i] !== 0) {
      nums[nonZeroIndex] = nums[i]
      nonZeroIndex++
    }
  }

  for (i = nonZeroIndex; i < nums.length; i++) {
    nums[i] = 0
  }

  return nums
}
```
