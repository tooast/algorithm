### :page_facing_up: Description

Count how many `1` in binary representation of a 32-bit integer.

### :pushpin: Example

Given `32`, return `1`

Given `5`, return `2`

Given `1023`, return `9`

### :bulb: Solution

```python
class Solution:
    # @param num: an integer
    # @return: an integer, the number of ones in num
    def countOnes(self, num):
        # count = 0
        # while num and count != 32:
        #     num = num & (num - 1)
        #     count += 1
        # return count
        return sum([(num>>i & 1) for i in range(0,32)])
```





