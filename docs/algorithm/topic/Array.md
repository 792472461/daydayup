# 数组

## 11.盛水最多的容器

<<< @/algorithm/topic/Array/11.盛最多水的容器.js

## 26.删除有序数组中的重复项

<<< @/algorithm/topic/Array/26.删除有序数组中的重复项.js

## 35.搜索插入位置

<<< @/algorithm/topic/Array/35.搜索插入位置.js

## 53.最大子序和

<<< @/algorithm/topic/Array/53.最大子序和.js

## 75.颜色分类

<<< @/algorithm/topic/Array/75.颜色分类.js
## 167.两数之和 II - 输入有序数组

```javascript
/**
 * @param {number[]} numbers
 * @param {number} target
 * @return {number[]}
 */
export const twoSum = function (numbers, target) {
    let i = 0
    let j = numbers.length - 1
    while (i < numbers.length) {
      if (numbers[i] + numbers[j] === target) return [i + 1, j + 1]
      j--
      if (j === i) {
        i++
        j = numbers.length - 1
      }
    }
  }

```

## 215.数组中的第K个最大元素

```javascript
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {number}
 */
export const findKthLargest = function (nums, k) {
    /**
     * 数组辅助函数，调换位置
     * @param {number[]} arr 原数组
     * @param {number} i 下标i
     * @param {number} j 下标j
     */
    const swap = (arr, i, j) => {
      const temp = arr[i]
      arr[i] = arr[j]
      arr[j] = temp
    }
    /**
     * partition函数
     * @param {number[]} arr 数组
     * @param {number} l 左边标定点
     * @param {number} r 右边标定点
     * @returns {number} 标定点
     */
    const partition = (arr, l, r) => {
      swap(arr, l, Math.floor(Math.random() * (r - l + 1) + l))

      // arr[l+1...i-1] <= v; arr[j+1...r] >= v
      let i = l + 1
      let j = r
      while (true) {
        while (i <= j && arr[i] < arr[l]) {
          i++
        }

        while (j >= i && arr[j] > arr[l]) {
          j--
        }

        if (i >= j) break
        swap(arr, i, j)

        i++
        j--
      }
      swap(arr, l, j)
      return j
    }
    /**
     * 获取k大的数
     * @param {number[]} arr
     * @param {number} l
     * @param {number} r
     * @param {*} k
     * @returns {number}
     */
    const selectK = (arr, l, r, $k) => {
      const p = partition(arr, l, r)

      if ($k === p) return arr[p]

      if ($k < p) return selectK(arr, l, p - 1, $k)
      return selectK(arr, p + 1, r, $k)
    }
    return selectK(nums, 0, nums.length - 1, nums.length - k)
  }

```

## 278.第一个错误的版本

```javascript
/**
 * Definition for isBadVersion()
 *
 * @param {integer} version number
 * @return {boolean} whether the version is bad
 * isBadVersion = function(version) {
 *     ...
 * };
 */

/**
 * @param {function} isBadVersion()
 * @return {function}
 */
export const solution = function (isBadVersion) {
  /**
   * @param {integer} n Total versions
   * @return {integer} The first bad version
   */
  return function (n) {
    let l = 1
    let r = n
    while (l < r) {
      const mid = Math.floor(l + (r - l) / 2)
      if (isBadVersion(mid)) {
        r = mid
      } else {
        l = mid + 1
      }
    }
    return l
  }
}

```

## 283.移动零

```javascript
/**
 * @param {number[]} nums
 * @return {void} Do not return anything, modify nums in-place instead.
 */
export const moveZeroes = function (nums) {
    let n = 0
    for (let i = 0; i < nums.length; i++) {
      if (nums[i] !== 0) {
        nums[n] = nums[i]
        n++
      }
    }
    while (n < nums.length) {
      nums[n] = 0
    }
  }

```

## 704.二分查找

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
export const search = function (nums, target) {
    /**
     * @param {*} nums
     * @param {number} l
     * @param {*} r
     * @param {*} target
     */
    const _search = ($nums, l, r, $target) => {
      if (l > r) return -1
      const mid = Math.floor(l + (r - l) / 2)
      if ($nums[mid] === $target) return mid
      if ($nums[mid] < $target) return _search($nums, mid + 1, r, $target)
      return _search($nums, 0, mid - 1, $target)
    }
    return _search(nums, 0, nums.length - 1, target)
  }

// 非递归实现
const search2 = function (nums, target) {
  let l = 0
  let r = nums.length - 1
  // 要搜索的范围
  while (l <= r) {
    const mid = Math.floor(l + (r - l) / 2)
    if (nums[mid] === target) return mid
    if (nums[mid] < target) l = mid + 1
    else r = mid - 1
  }
  return -1
}

console.log(search2([-1, 0, 3, 5, 9, 12], 9))

```

## 912.排序数组

```javascript
/**
 * @param {number[]} nums
 * @return {number[]}
 */
export const sortArray = function (nums) {
    /**
     * 数组辅助函数，调换位置
     * @param {number[]} arr 原数组
     * @param {number} i 下标i
     * @param {number} j 下标j
     */
    const swap = (arr, i, j) => {
      const temp = arr[i]
      arr[i] = arr[j]
      arr[j] = temp
    }
    /**
     * 排序函数
     * @param {number[]}} arr 数组
     * @param {number} l 左边标定点
     * @param {number} r 右边标定点
     */
    const sort = (arr, l, r) => {
      if (l >= r) return
      // 添加随机化
      swap(arr, l, Math.floor(Math.random() * (r - l + 1) + l))

      // arr[l + 1, lt] < v, arr[lt + 1, i - 1] == v, arr[gt, r] > v
      let lt = l
      let i = l + 1
      let gt = r + 1
      while (i < gt) {
        if (arr[i] < arr[l]) {
          lt++
          swap(arr, i, lt)
          i++
        } else if (arr[i] > arr[l]) {
          gt--
          swap(arr, i, gt)
        } else {
          // arr[i] === arr[l]
          i++
        }
      }
      swap(arr, l, lt)
      // arr[l, lt - 1] < v, arr[lt, gt - 1] == v, arr[gt, r] > v
      sort(arr, l, lt - 1)
      sort(arr, gt, r)
    }
    sort(nums, 0, nums.length - 1)
    return nums
  }

```

## 977.有序数组的平方

```javascript
/**
 * 977. 有序数组的平方
 * @param {number[]} nums
 * @return {number[]}
 */
export const sortedSquares = function (nums) {
    const res = []
    let i = 0
    let j = nums.length - 1

    while (i <= j) {
      const l = Math.abs(nums[i])
      const r = Math.abs(nums[j])
      if (l > r) {
        res.unshift(l * l)
        i++
      } else {
        res.unshift(r * r)
        j--
      }
    }
    return res
  }

```

## 1234.替换子串得到平衡字符串

```javascript
/**
 * @param {string} s
 * @return {number}
 */
const balancedString = function (s) {
    const n = s.length
    const num = new Array(n + 1).fill().map(() => {
      return new Array(4).fill()
    })
    for (let i = 1; i <= n; i++) {
      for (let j = 0; j < 4; j++) {
        num[i][j] = num[i - 1][j]
      }
      console.log(num)
      ++num[i]['QWER'.indexOf(s.charAt(i - 1))]
    }
    let r = n
    for (let i = 0, j = 0, m = n / 4; j <= n; ++i) {
      for (j = Math.max(i, j); j <= n && (
        num[n][0] + num[i][0] - num[j][0] > m ||
        num[n][1] + num[i][1] - num[j][1] > m ||
        num[n][2] + num[i][2] - num[j][2] > m ||
        num[n][3] + num[i][3] - num[j][3] > m
      ); ++j) {
        if (j <= n) {
          r = Math.min(r, j - i)
        }
      }
    }
    return r
  }

console.log(balancedString('QWER'))

```

## 1248.统计[优美子数组]

```javascript
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {number}
 */
const numberOfSubarrays = function (nums, k) {
    const n = nums.length
    const s = new Array(n + 1).fill(0)
    s[0] = 0
    for (let i = 1; i <= n; i++) {
      s[i] = s[i - 1] + nums[i - 1] % 2
    }
    const count = new Array(n + 1).fill(0)
    let ans = 0
    count[s[0]]++
    for (let i = 1; i <= n; i++) {
      if (s[i] - k >= 0) {
        ans += count[s[i] - k]
      }
      count[s[i]]++
    }
    return ans
  }

console.log(numberOfSubarrays([1, 1, 2, 1, 1], 3))
console.log(numberOfSubarrays([2, 4, 6], 3))
console.log(numberOfSubarrays([2, 2, 2, 1, 2, 2, 1, 2, 2, 2], 2))

```

## 剑指 Offer 40. 最小的k个数

```javascript
/**
 * 数组辅助函数，调换位置
 * @param {number[]} arr 原数组
 * @param {number} i 下标i
 * @param {number} j 下标j
 */
const swap = (arr, i, j) => {
    const temp = arr[i]
    arr[i] = arr[j]
    arr[j] = temp
  }
/**
 * partition函数
 * @param {number[]} arr 数组
 * @param {number} l 左边标定点
 * @param {number} r 右边标定点
 * @returns {number} 标定点
 */
const partition = (arr, l, r) => {
  swap(arr, l, Math.floor(Math.random() * (r - l + 1) + l))

  // arr[l+1...i-1] <= v; arr[j+1...r] >= v
  let i = l + 1
  let j = r
  while (true) {
    while (i <= j && arr[i] < arr[l]) {
      i++
    }

    while (j >= i && arr[j] > arr[l]) {
      j--
    }

    if (i >= j) break
    swap(arr, i, j)

    i++
    j--
  }
  swap(arr, l, j)
  return j
}
/**
 * 获取k大的数
 * @param {number[]} arr
 * @param {number} l
 * @param {number} r
 * @param {*} k
 * @returns {number}
 */
const selectK = (arr, l, r, k) => {
  const p = partition(arr, l, r)

  if (k === p) return arr[p]

  if (k < p) return selectK(arr, l, p - 1, k)
  return selectK(arr, p + 1, r, k)
}

/**
 * @param {number[]} data
 * @param {number} k
 * @return {number[]}
 */
export const getLeastNumbers = function (data, k) {
  selectK(data, 0, data.length - 1, k - 1)
  return data.slice(0, k)
}

```

## 剑指 Offer 51. 数组中的逆序对

```javascript
/**
 * 这道题可以巧妙利用归并排序的思想
 * @param {number[]} nums
 * @return {number}
 */
export const reversePairs = function (nums) {
    return mergeSort(nums)
  }

/**
 * 排序
 * @param {number[]} arrData
 * @returns {number}
 */
const mergeSort = (arrData) => {
  /**
   * 合并两个有序的数组，arr[l, mid] 和 arr[mid + 1, r]
   * @param {number[]} arr
   * @param {number} l
   * @param {number} mid
   * @param {number} r
   * @param {number[]} temp
   * @returns {number}
   */
  const merge = (arr, l, mid, r, temp) => {
    temp = arr.slice(l, r + 1)
    let rest = 0
    let i = l
    let j = mid + 1
    // 每轮为arr[k]赋值，从l走到r
    for (let k = l; k <= r; k++) {
      if (i > mid) {
        // 索引i大于 中间值的时候  就越界了直接赋值
        arr[k] = temp[j - l]
        j++
      } else if (j > r) {
        // 索引i 大于右边边界的时候 直接赋值
        arr[k] = temp[i - l]
        i++
      } else if (temp[i - l] <= temp[j - l]) {
        // 左边元素比右边元素小的时候
        arr[k] = temp[i - l]
        i++
      } else {
        rest += mid - i + 1
        arr[k] = temp[j - l]
        j++
      }
    }
    return rest
  }
  /**
   * 排序过程
   * @param {number[]} arr
   * @param {number} l
   * @param {number} r
   * @param {number[]} temp
   */
  const sort = (arr, l, r, temp) => {
    if (l >= r) return 0
    let rest = 0
    const mid = l + Math.floor((r - l) / 2)
    rest += sort(arr, l, mid, temp)
    rest += sort(arr, mid + 1, r, temp)
    if (arr[mid] > arr[mid + 1]) {
      rest += merge(arr, l, mid, r, temp)
    }
    return rest
  }
  const temp = [...arrData]
  return sort(arrData, 0, arrData.length - 1, temp)
}

```

## 300.最长递增子序列

```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
const lengthOfLIS = function (nums) {
    const n = nums.length
    if (n <= 1) return n
    const dp = [null, nums[0]]
    let max = 1
    for (let i = 1; i < n; i++) {
      if (dp[max] < nums[i]) {
        dp[++max] = nums[i]
        continue
      }
      let pos = 0
      let left = 1
      let right = max
      while (left <= right) {
        const mid = left + right >> 1
        if (nums[i] > dp[mid]) {
          left = mid + 1
          pos = mid
        } else {
          right = mid - 1
        }
      }
      dp[pos + 1] = nums[i]
    }
    return max
  }

lengthOfLIS([10, 9, 2, 5, 3, 7, 101, 18])
```
