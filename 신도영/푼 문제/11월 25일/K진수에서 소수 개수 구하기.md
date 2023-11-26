import java.util.*;
class Solution {
​    public int solution(int n, int k) {
​        int answer = 0;
​        Stack<Integer> stk = new Stack<>();
​        while(n>=k){
​            stk.push(n%k);
​            n=n/k;
​        }
​        stk.push(n);
​        StringBuilder sb = new StringBuilder();
​        while(!stk.isEmpty()){
​            sb.append(stk.pop());
​        }
​        StringTokenizer st = new StringTokenizer(sb.toString(),"0");
​        int st_cnt = st.countTokens();
​        for(int i=0;i<st_cnt;i++){
​            String s = st.nextToken();
​            long is_prime = Long.parseLong(s);
​            int flag = 0;
​            long max = (long)Math.sqrt(is_prime);
​            for(int j=2;j<=max;j++){
​                if(is_prime%j==0){
​                    flag = 1;
​                    break;
​                }
​            }
​            if(is_prime == 1){
​                flag=1;
​            }
​            if(flag == 0) {
​                answer++;
​            }
​        }
​        
        return answer;
    }
}