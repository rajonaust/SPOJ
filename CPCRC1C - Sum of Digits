/*
    Author : RAJON BARDHAN
    AUST CSE 27th Batch
    All my programming success are dedicated to my mom , dad , little sister madhobi , teachers , friends and love TANIA SULTANA RIMY

    Problem Name : CPCRC1C - Sum of Digits ( SPOJ )
    ALGORITHM : Dynamic Programming
*/

#include <bits/stdc++.h>
using namespace std;

#define pb push_back
#define ff first
#define ss second
#define mp make_pair
#define memo(a,b) memset(a,b,sizeof(a))
#define INF 1e9
#define EPS 1e-8
#define PI 3.14159265358979323846

typedef long long ll ;
typedef unsigned long long ull ;

/* int dx[] = {1,-1,0,0} , dy[] = {0,0,1,-1}; */ // 4 Direction
/* int dx[] = {1,-1,0,0,1,1,-1,-1} , dy[] = {0,0,1,-1,1,-1,1,-1}; */ // 8 Direction
/* int dx[] = {1,-1,1,-1,2,2,-2,-2} , dy[] = {2,2,-2,-2,1,-1,1,-1}; */ // Knight Direction
/* int dx[] = {2,-2,1,1,-1,-1} , dy[] = {0,0,1,-1,1,-1}; */ // Hexagonal Direction

vector <int> V ;
ll dp[20] , fp[20] ;

void init(ll number)
{
    V.clear();
    while(number!=0)
    {
        V.pb(number%10);
        number/=10;
    }
}

pair<ll,ll> answer(int pos,bool flag)
{
    if(pos==-1) return mp(1,0) ;

    if(flag==0&&dp[pos]!=-1) return mp(dp[pos],fp[pos]) ;
    ll ret = 0 , f = 0 ;

    int ending ;
    if(flag) ending = V[pos] ; else ending = 9 ;

    for(int i=0;i<=ending;i++)
    {
        pair<ll,ll> prv = answer(pos-1,flag&&i==ending) ;
        ret = ret+prv.ff;
        f = f + i*prv.ff + prv.ss ;
    }

    if(flag==0) dp[pos] = ret , fp[pos] =f ;

    return mp(ret,f) ;
}

ll solve(ll number)
{
    init(number);
    return answer(V.size()-1,1).ss ;
}

int main()
{
    //freopen("input.txt","r",stdin);
    //freopen("output.txt","w",stdout);
    memo(dp,-1);
    ll a , b ;
    while(scanf("%lld%lld",&a,&b)==2&&a!=-1&&b!=-1)
    {
        printf("%lld\n",solve(b)-solve(a-1));
    }
    return 0;
}
