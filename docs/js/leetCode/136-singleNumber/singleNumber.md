# 136. Single Number

> Given a non-empty array of integers, every element appears twice except for one. Find that single one.
>
> Note: Your algorithm should have a linear runtime complexity. Could you implement it without using extra memory?

### Example:

#### 1.

```
Input: [2, 2, 1]
Output: 1
```

#### 2.

```
Input: [4, 1, 2, 1, 2]
Output: 4
```

### Solution:

#### 1.

```javascript
function singleNumber(nums) {
  return nums.reduce((prev, curr) => prev ^ curr, 0);
}
```

#### 2.

```javascript
function singleNumber(nums) {
  var data = {};
  nums.forEach(num => {
    if (data[num] === undefined) {
      data[num] = 1;
    } else {
      delete data[num];
    }
  });
  return Number(Object.keys(data)[0]);
}
```

#### 3.

```javascript
function singleNumber(nums) {
  var result = nums[0];
  for (var i = 1; i < nums.length; i++) {
    result = result ^ nums[i];
  }
  return result;
}
```
