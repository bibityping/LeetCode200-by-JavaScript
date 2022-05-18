# Leetcode 题解 - 数组与矩阵

---

- [Leetcode 题解 - 数组与矩阵](#leetcode-题解---数组与矩阵)
    - [LeetCode 题解 - #283 移动零](#leetcode-题解---283-移动零)
      - [题目](#题目)
      - [JavaScript 题解](#javascript-题解)

### LeetCode 题解 - #283 移动零

---

#### 题目

给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

请注意  ，必须在不复制数组的情况下原地对数组进行操作。

示例 1:

```
输入: nums = [0,1,0,3,12]
输出: [1,3,12,0,0]
```

示例 2:

```
输入: nums = [0]
输出: [0]
```

提示:

- `1 <= nums.length <= 10^4^`
- `-2^31^ <= nums[i] <= 2^31^ - 1`

进阶：你能尽量减少完成的操作次数吗？

> 📌 思路：将所有非零的数移到数字前面，数组后面的数填上零即可。

#### JavaScript 题解

---

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
