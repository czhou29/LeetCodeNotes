## 151 Reverse Words in a String

```python
class Solution:
    def reverseWords(self, s: str) -> str:
        a = s.strip().split()
        a.reverse()
        return " ".join(a)
```

