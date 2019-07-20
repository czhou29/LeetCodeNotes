## 345 Reverse Vowels of a String

```c++
class Solution {
public:
    bool cv(char c){
        if(c=='a'||c=='e'||c=='i'||c=='o'||c=='u'||c=='A'||c=='E'||c=='I'||c=='O'||c=='U') return true;
        return false;
    }
    string reverseVowels(string s) {
        int n = s.size() - 1;
        int i = 0, j = n;
        while(i<j){
            while(i < n && !cv(s[i])) i++;
            while(j >= 0 && !cv(s[j])) j--;
            if(i<n && j >= 0 && i < j && cv(s[i]) && cv(s[j])){
                swap(s[i], s[j]);
                i++, j--;
            }
        }
        return s;
    }
};
```

