Language: C++14

#include <bits/stdc++.h>
using namespace std;
 
#define fast { ios :: sync_with_stdio(false); cin.tie(0); cout.tie(0); }
#define pb push_back
#define ll long long
 
#define vi vector<int>
#define vl vector<long>
#define vll vector<long long>
 
#define infi INT_MAX
#define infl LONG_MAX
#define f(i,a,b) for(ll i=a;i<b;i++)
#define fi(i,a,b) for(ll i=(b-1);i>=a;i--)
#define F first
#define S second
#define G(a,b) get<a>(b)
#define MP make_pair
#define MT make_tuple
#define pll pair<ll,ll> 
 
long double inc=0.0001;
long double pi=3.14159265359;
long double b,c;

inline bool check(long double &x)
{
  if( (2*x+b)*((long double)sin(x)) <= (x*x+b*x+c)*((long double)cos(x)) ) return 0;
  return 1;
}

void func()
{ 
 cin>>b>>c;
 //cout<<b<<" "<<c<<endl;
 long double l=inc,r=(pi/2)-inc,ans1=-1,ans2=-1,mid;
 while(l<=r)
 {
   mid=(l+r)/2;
   if(check(mid)==0)
   {
    ans1=mid;
    l=mid+inc;
   }
   else r=mid-inc;
 }

 l =inc,r=(pi/2)-inc;
 while(l<=r)
 {
   mid=(l+r)/2;
   if(check(mid)==1)
   {
    ans2=mid;
    r=mid-inc;
   }
   else l=mid+inc;
 }

 long double x1=(ans1*ans1+b*ans1+c)/((long double)sin(ans1));
 long double x2=(ans2*ans2+b*ans2+c)/((long double)sin(ans2));
 if(x2>x1) x1=x2;
 printf("%0.8Lf\n",x1 );

} 
 
int main() 
{
    fast
    //freopen("input.txt","r",stdin); freopen("output.txt","w",stdout);
    
    ll q=1;
    cin>>q;
 
    while(q)
    {
      func();
      q--;
    }
 
    return 0;
}

