#include <string>
#include <vector>
#include <string>
#include <algorithm>
#include <cmath>

using namespace std;
int answer = 0;

bool countPrimeNumbers(string str){
if(str== "1" && str =="1"){
return false;
}
long long num = stoll(str);
for(long long i=2; i<=sqrt(num); i++){
if(num % i == 0){
return false;
}
}
return true;
}

vector<string> split(string input, string delimeter){
vector<string> ret;
int pos = 0;
string token = "";
while((pos = input.find(delimeter)) != string::npos){
token = input.substr(0, pos);
if(!token.empty())
ret.push_back(token);
input.erase(0, pos+delimeter.length());  
 }
if(!input.empty())
ret.push_back(input);
return ret;
}

int solution(int n, int k) {
string s = "";
while(n!=0){
int rest = n%k;
s+=to_string(rest);
n/=k;
}
reverse(s.begin(), s.end());
string d = "0";
vector<string> num = split(s, d);
for(int i=0;i<num.size();i++){
bool isPrime = countPrimeNumbers(num[i]);
if(isPrime)
answer++;
}
return answer;
}
