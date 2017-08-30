### :page_facing_up: Description

Partition an integers array into odd number first and even number second.

### :pushpin: Example

Given `[1, 2, 3, 4]`, return `[1, 3, 2, 4]`

### :bulb: Solution

```python
class Solution:
    # @param nums: a list of integers
    # @return: nothing
    def partitionArray(self, nums):
        left, right = 0, len(nums) - 1
        while left < right:
            while (nums[left] & 1) and left < right:
                left += 1
            while not (nums[right] & 1) and left < right:
                right -= 1
            nums[left], nums[right] = nums[right], nums[left]
```





