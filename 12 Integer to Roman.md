## 12 Integer to Roman

```c++
class Solution {
public:
    string intToRoman(int num) {
        int d[] = {1, 4, 5, 9, 10, 40, 50, 90, 100, 400, 500, 900, 1000};
        string str[] = {"I", "IV", "V", "IX", "X", "XL", "L", "XC", "C", "CD", "D", "CM", "M"};           string res = "";
        for(int i = 12; i >= 0; i--) {
            while(num >= d[i]) {
                num -= d[i];
                res += str[i];
            }
        }
        return res;
    }
};
```

