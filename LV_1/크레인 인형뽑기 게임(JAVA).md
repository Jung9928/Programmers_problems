```JAVA
import java.util.*;

class Solution {
    public int solution(int[][] board, int[] moves) {
        int answer = 0;
        
        Stack<Integer> bucket = new Stack<>();

        for(int pos : moves) {
            for(int i=0; i<board.length; i++) {
                if(board[i][pos-1] != 0) {
                    
                    if(bucket.isEmpty()) {
                        bucket.push(board[i][pos-1]);
                    }
                    else {
                        if(bucket.peek() == board[i][pos-1]) {
                            bucket.pop();
                            answer += 2;
                        }
                        else {
                            bucket.push(board[i][pos-1]);
                        }
                    }
                    
                    board[i][pos-1] = 0;
                    break;
                }
            }
        }  
        return answer;
    }
}
```
