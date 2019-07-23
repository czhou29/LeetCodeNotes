## 125 Valid Palindrome

```c++
class Solution {
public:
    bool check(char c) {
        return (c >= 'a' && c <= 'z') || (c >= 'A' && c <= 'Z') || (c >= '0' && c <= '9');
    }
    
    bool isPalindrome(string s) {
        transform(s.begin(), s.end(), s.begin(), ::tolower);  
        int i = 0, j = s.size() - 1;
        while(i < j) {
            while(i < j && !(check(s[i]))) i++;
            while(i < j && !(check(s[j]))) j--;
            if(s[i] != (s[j] ^ 32) && s[i] != s[j]) return false;
            i++, j--;
        }
        return true;
    }
};
```

