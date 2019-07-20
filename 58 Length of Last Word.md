## 58 Length of Last Word

### 自己

```c++
class Solution {
public:
    int lengthOfLastWord(string s) {
        int length = 0;
        bool flag = false;
        for(int i = s.size() - 1; i >= 0; i--){
            if(s[i] == ' ' && !flag) continue;
            else if(s[i] == ' ' && flag) return length;
            else{
                flag = ~flag;
                length++;
            }
        }
        return length;
    }
};
```

### StringStream做法

```c++
class Solution {
public:
    int lengthOfLastWord(string s) {
        stringstream ss(s);
        string c;
        while (ss >> c);
        return c.size();
    }
};
```

