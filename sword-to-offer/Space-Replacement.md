### :page_facing_up: Description

Write a method to replace all spaces in a string with `%20`. The string is given in a characters array, you can assume it has enough space for replacement and you are given the true length of the string.

You code should also return the new length of the string after replacement.

### :pushpin: Example

Given `"Mr John Smith"`, length = `13`.

The string after replacement should be `"Mr%20John%20Smith"`, you need to change the string in-place and return the new length `17`.

### :bulb: Solution

```python
class Solution:
    """
    @param: string: An array of Char
    @param: length: The true length of the string
    @return: The true length of new string
    """
    def replaceBlank(self, string, length):
        space_num = 0
        if not string: return
        for ch in string:
            if ch == ' ':
                space_num += 1
        if space_num == 0:
            return length
        string.extend([0] * space_num * 2)
        new_length = length + space_num * 2 - 1
        for i in range(length)[::-1]:
            if string[i] == ' ':
                string[new_length] = '0'
                new_length -= 1
                string[new_length] = '2'
                new_length -= 1
                string[new_length] = '%'
                new_length -= 1
            else:
                string[new_length] = string[i]
                new_length -= 1
        return length + space_num * 2
```





