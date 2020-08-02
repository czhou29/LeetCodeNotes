## 3 Longest Substring Without Repeating Characters

```java
class Solution {
    public int lengthOfLongestSubstring(String s) {
        int left = 0, right = 0;
        int maxl = 0, maxr = 0, l = 0;
        Map<Character, Integer> map = new HashMap<>();
        for (int i = 0; i < s.length(); i++) {
            right ++;
            map.put(s.charAt(i), map.getOrDefault(s.charAt(i), 0)+1);
            while (map.get(s.charAt(i)) > 1) {
                map.put(s.charAt(left), map.get(s.charAt(left))-1);
                left ++;
            }
            if (right - left > l) {
                maxl = left;
                maxr = right;
                l = right - left;
            }
        }
        return l;
    }
}
```

