# largest-of-pf

#include <iostream>
#include<cmath>
using namespace std;
long long getMaxPrimefactor(long long n) {
   long long maxPF = -1;
   while (n % 2 == 0) {
      maxPF = 2;
      n /= 2;
   }
   int t;
   while(t--){
   for (int i = 3; i <= sqrt(n); i += 2) {
      while (n % i == 0) {
         maxPF = i;
         n = n / i;
      }
   }
   }
   if (n > 2)
   maxPF = n;
   return maxPF;
}
int main() {
   long long n = 162378;
   cout << "Max Prime factor of " << n << " is " << getMaxPrimefactor(n);
}
