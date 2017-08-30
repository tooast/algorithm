### :page_facing_up: Description

Suppose a sorted array is rotated at some pivot unknown to you beforehand.

(i.e., `0 1 2 4 5 6 7` might become `4 5 6 7 0 1 2`).

Find the minimum element.

### :pushpin: Example

Given `[4, 5, 6, 7, 0, 1, 2]` return `0`

### :bulb: Solution

```python
class Solution:
    # @param nums: a rotated sorted array
    # @return: the minimum number in the array
    def findMin(self, nums):
        if not nums:
            return nums
        lo, hi = 0, len(nums) - 1
        while lo < hi:
            mid = lo + (hi - lo) / 2
            if nums[mid] > nums[hi]:
                lo = mid + 1
            elif nums[mid] < nums[hi]:
                hi = mid
            else:
                if nums[hi] > nums[hi-1]:  # when duplicate occurs
                    lo = hi - 1
                    break
                hi -= 1
        return nums[lo]
```







