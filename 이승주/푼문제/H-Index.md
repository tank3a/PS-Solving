#include <string>
#include <vector>
#include <algorithm>

using namespace std;

int solution(vector<int> citations) {
int answer = 0;
sort(citations.begin(), citations.end());
int max = citations.back();
for(int i=0;i<=max;i++){ //인용된 횟수를 0부터 벡터의 최대값까지
int cnt = 0;
int j = 0;
while(i>citations[j]){ // h번 미만으로 인용된 논문의 개수 구하기
cnt++;
j++;
}
if(citations.size()-cnt >= i && cnt <= i){
if(answer <= i)
answer = i;
}
}
return answer;
}
