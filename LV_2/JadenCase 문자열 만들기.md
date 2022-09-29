## JAVA 풀이
```JAVA
```

## C++ 풀이
```C++
#include <string>
#include <vector>
#include <cctype>
#include <algorithm>
#include <iostream>

using namespace std;

string solution(string s) {
    string answer = "";
    
    answer += toupper(s[0]);
    for(int i=1; i<s.size(); i++)
    {
        if(isblank(s[i-1]) != 0)    // 공백이라면
            answer += toupper(s[i]);
        else
            answer += tolower(s[i]);
    } 
    return answer;
}
```
