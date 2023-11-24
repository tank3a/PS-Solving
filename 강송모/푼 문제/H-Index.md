//문제 링크 : https://school.programmers.co.kr/learn/courses/30/lessons/42747
```
import java.util.*;

class Solution {
    public int solution(int[] citations) {
        int answer = 0;
        
        Arrays.sort(citations);
        
        int len = citations.length;
        
        for (int i = len - 1; i > -1; i--) {
            if (len - i <= citations[i]) {
                answer += 1;
            } else {
                break;
            }
        }
        
        return answer;
    }
}
```