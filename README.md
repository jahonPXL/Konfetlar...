# KONFETLAR
#include <bits/stdc++.h> 
#define ll long int 
using namespace std;
int main(){     
ios_base::sync_with_stdio(false);cin.tie(0);cout.tie(0);     
  int n,k;
    cin >> n;
    cin >> k;
    ll a[n];
    ll s[n+1] = {0};
    for(int i = 0; i < n; i++) 
    cin >> a[i];
    sort(a,a+n);
    s[0] = 0;    
    for(int i = 1; i <= n; i++) 
    s[i] = s[i-1]+a[i-1];
        ll t = 0;     
    for(int i = 0; i < k; i++) 
    t += s[k]-s[i]-(k-i)*a[i];
    ll m = t;
    for(int i = 0; i < n-k; i++){
    t += (k-1)*(a[i]+a[k+i])-2*(s[k+i]-s[i+1]);
    m = min(m,t);  
    }
    cout << m;
  
}
