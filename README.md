# 在“有效的括号中”，if not stack or stack[-1] != mapping[char]:和if stack[-1] != mapping[char] or not stack:是有区别的
```python
class solution:
  def solve(self,s:str):->bool
    stack=[]
    dic={"}":"{",")":"(","]":"["}
    for char in s:
      if char in dic.values():#寻找左括号
        stack.append(char)
      elif char in dic:
        if not stack or stack[-1]!=dic[char]:
          return False
        stack.pop()
    return not stack
```
##因为如果此时stack为空，会先判断stack[-1]，这会报错
