## 929 Unique Email Addresses

```c++
class Solution {
public:
    int numUniqueEmails(vector<string>& emails) {
        unordered_set<string> set;
        for(auto s: emails) {
            string local, domain;
            int k = 0;
            while(s[k] != '@') k++;
            local = s.substr(0, k);
            domain = s.substr(k+1);
            string newLocal;
            for(auto c: local){
                if(c == '+') break;
                if(c != '.') newLocal += c;
            }
            set.insert(newLocal + '@' + domain);
        }
        return set.size();
    }
};
```

