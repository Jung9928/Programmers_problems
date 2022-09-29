## JAVA 풀이
```JAVA
import java.util.*;

class Solution {
    boolean solution(String s) {
        boolean answer = true;
        int yCnt=0, pCnt=0;
        char[] temp = s.toCharArray();
        
        for(int i=0; i<temp.length; i++)
        {
            if(temp[i] == 'y' || temp[i] == 'Y')
                yCnt++;
            if(temp[i] == 'p' || temp[i] == 'P')
                pCnt++;
        }
        
        if(pCnt == yCnt)
            answer = true;
        else
            answer = false;

        return answer;
    }
}
```

## C++ 풀이
```C++
#include <string>
#include <iostream>
using namespace std;

bool solution(string s)
{
    bool answer = true;
    int p_cnt = 0;
    int y_cnt = 0;
    
    // 'p', 'y' 모두 없는 경우 (대소문자 구별 x)
    for(auto c : s)
    {
        if(c == 'p' || c == 'P')
            p_cnt++;
        if(c == 'y' || c == 'Y')
            y_cnt++;
    }
    
    // p와 y의 개수가 같은 경우
    if(p_cnt == y_cnt)
        answer = true;
        
    // p와 y 모두 하나도 없는 경우
    if(p_cnt == 0 && y_cnt == 0)
        answer = true;
        
    // p와 y의 개수가 다른 경우
    if(p_cnt != y_cnt)
    {
        // p 또는 y가 하나이상 존재도 하는 경우
        if(p_cnt > 0 || y_cnt > 0)
            answer = false;
    }

    return answer;
}
```
