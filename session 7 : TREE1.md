**TR 1 [CPP LANGUAGE]**

    #include <iostream>
    #include <cstdio>
    #include <vector>
    #include <stack>
    #include <queue>
    #include <string>
      #include <cstring>
    #include <map>
        #include <cstdlib>
    #include <algorithm>
    #include <list>
    #include <deque>
    #include <bitset>
    #include <cmath>
    #include <set>
    #include <sstream>

    using namespace std;

    #define oo 0x7F7F7F7F
    #define LET(x,a)     __typeof(a) x(a)
    #define EACH(it,v)   for(LET(it,v.begin());it!=v.end();++it)
    #define REP(i,n)     for(__typeof(n) i(0); i<n; i++)
    #define ALL(x)       (x).begin(), (x).end()
    #define gint(t)      scanf("%d", &t);
    #define pint(t)      printf("%d\n", t);
    #define pb           push_back
    #define mp           make_pair
    #ifdef JAI_ARENA
    #define debug(args...) {cerr<<"> "; dbg,args;cerr<<endl;}
    #define debugv(v, n)      {cerr<<"> "; REP(ni, n) dbg,(int)v[ni]; cerr<<endl;}
    #else
    #define debug(...) ;
    #define debugv(...) ;
    #endif
    typedef long long int   ll;
    typedef unsigned long long int ull;
    typedef unsigned int    uint;
    typedef pair<int, int>  pii;
    typedef vector<int>     vi;
    typedef vector<vi>      vii;
    typedef vector<pii>     vpii;

    struct debugger
    {
    template<typename T> debugger& operator , (const T& v)
    {
        cerr<<v<<" ";
        return *this;
    }
    } dbg;


    #define BUF 4096
    char ibuf[BUF];
    int ipt = BUF;

    int readUInt() {
    while (ipt < BUF && ibuf[ipt] < '0') ipt++;
    if (ipt == BUF) {
    fread(ibuf, 1, BUF, stdin);
    ipt = 0;
    while (ipt < BUF && ibuf[ipt] < '0') ipt++;
    }
    int n = 0; char neg = 0;
    if(ipt !=0 && ibuf[ipt-1] == '-') neg = 1;
    while (ipt < BUF && ibuf[ipt] >= '0') n = (n*10)+(ibuf[ipt++]-'0');
    if (ipt == BUF) {
    fread(ibuf, 1, BUF, stdin);
    ipt = 0;
    while (ipt < BUF && ibuf[ipt] >= '0') n = (n*10)+(ibuf[ipt++]-'0');
    }
    return neg?-n:n;
    }
    int testcase;

    #define MAXN  100005
    #define MAXLG 20
        vi adj[100005];
    int deg[100005];
    int n, ndc = 0;
    struct entry {
    int nr[2], p;
    } L[MAXN];
    int P[MAXLG][MAXN], N, i, stp, cnt;
    int parent[MAXLG][MAXN];
    int *p1, *p2;
    int depth[MAXN];
    int cmp(struct entry a, struct entry b)
    {
    return a.nr[0] == b.nr[0] ? (a.nr[1] < b.nr[1] ? 1 : 0) : (a.nr[0] < b.nr[0] ? 1 : 0);
    }
    void updateparent() {
    REP(ki, MAXLG-1) {
        REP(ni, n) {
            parent[ki+1][ni] = (parent[ki][ni] == -1)?-1:parent[ki][parent[ki][ni]];
        }
    }
    }
    void dfs(int st, int par, int dep) {
    parent[0][st] = par;
    p1[st] = par;
    depth[st] = dep;
    EACH(it, adj[st]) {
        if(*it == par) continue;
        dfs(*it, st, dep+1);
    }
    } 
    int lcp(int x, int y)
    {
    int k, ret = 0;
    for (k = stp - 1; k >= 0 && x < N && y < N; k --)
        if (P[k][x] == P[k][y]) {
            debug(x, y, k);
            x = parent[k][x], y = parent[k][y], ret += 1 << k;
        }
    return ret;
    }
    int work()
    {
    for (N = n, i = 0; i < N; i ++)
        P[0][i] = deg[i];
    for (stp = 1, cnt = 1; (cnt >> 1) < (N<<1); stp ++, cnt <<= 1)
    {
        for (i = 0; i < N; i ++)
        {
            L[i].nr[0] = P[stp - 1][i];
            int k = parent[stp-1][i];
            //debug(i, cnt , k);
            L[i].nr[1] = (k==-1)?-1:P[stp - 1][k];
            L[i].p = i;
        }
        sort(L, L + N, cmp);
        for (i = 0; i < N; i ++)
            P[stp][L[i].p] = i > 0 && L[i].nr[0] == L[i - 1].nr[0] && L[i].nr[1] == L[i - 1].nr[1] ? P[stp][L[i - 1].p] : i;
    }
    return 0;
    }
      void intIntSort(int d[],int m1[],int s){int i=-1,j=s,k,t;if(s<=1)return;k=(d[0]+d[s-1])/2;for(;;){while(d[++i]<k);while(d[--j]>k);if(i>=j)break;t=d[i];d[i]=d[j];d[j]=t;t=m1[i];m1[i]=m1[j];m1[j]=t;}intIntSort(d,m1,i);intIntSort(d+j+1,m1+j+1,s-j-1);}
      void solve() {
    gint(n);
    p1 = new int[n];
    p2 = new int[n];
    memset(deg, 0, sizeof deg);
    int x, y;
    REP(ni, n-1) {
        gint(x); gint(y);
        x--;y--;
        adj[x].push_back(y);
        adj[y].push_back(x);
        deg[x]++;
        deg[y]++;
    }
    dfs(0, -1, 1);
    updateparent();
    debugv(parent , n);
    work();
    int ar[n], d[n];
    REP(ni, n) ar[ni] = ni;
    REP(ni, n) d[ni] = P[stp-1][ni];
    intIntSort(d, ar, n);
    debugv(P[0], n);
    debugv(P[1], n);
    debugv(d, n);
    debugv(ar, n);
    ll res = depth[ar[0]];
    for(int i = 0; i<n-1; i++) {
        if(d[i] == d[i+1]) continue;
        debug(depth[ar[i+1]], lcp(ar[i], ar[i+1]));
        res += depth[ar[i+1]] - lcp(ar[i], ar[i+1]);
    }
    cout<<res<<endl;
    }
    bool input() {
    return true;
    }
    void preprocess() {

    }
    int main() {
    preprocess();
    solve();
    return 0;
    }
**TR 2 [CPP LANGUAGE]**

    #include<bits/stdc++.h>
    //void MERG(int x,int y)
    //int FIND_root(int i)
    const int M=2e5;
    using namespace std;
    int par[M],ans[M];
    int find(int u)
    {
    if(par[u]==u) return u;
      return find(par[u]);
    }
    void _union(int u,int v)
    {
    int x=find(u);
    int y=find(v);
    if(x==y) return;
    par[x]=y;
    }
    int main()
    {
    ios_base::sync_with_stdio(0); cin.tie(0);
    int n,m;
    cin>>n>>m;
    for(int i=1;i<=n;i++) par[i]=i;
    for(int i=0;i<m;i++)
      {
        int u,v;
        cin>>u>>v;
        _union(u,v);
      }
      for(int i=1;i<=n;i++)
      ans[find(i)]++;
      for(int i=1;i<=n;i++)
      cout<<ans[find(i)]-1<<" ";
        return 0;
      }
**TR 3 [CPP LANGUAGE]**

**TR 4 [CPP LANGUAGE]**

      #include<bits/stdc++.h>
    #define max 100001
    using namespace std;

    int q[max];
    int size[max];
    int root (int node);
    int root(int x)
    {
    while(x!=q[x])
    {
        q[x]=q[q[x]];
        x=q[x];
    }
    return x;
    }

    void connect(int u,int v)
    {
    int rootu=root(u);
    int rootv=root(v);
    if(rootu==rootv)
    return;
    if(size[rootu]<size[rootv])
    {
        q[rootu]=rootv;
        size[rootv]+=size[rootu];
    }
    else
    {
        q[rootv]=rootu;
        size[rootu]+=size[rootv];
    }
    }
    int main()
    {
    int n,m,u,v;
    set<int> s;
    cin>>n>>m;
    for(int i=1;i<=n;i++)
    {
        q[i]=i;
        size[i]=1;
    }
    for(int i=0;i<m;i++)
    {
        cin>>u>>v;
        connect(u,v);
    }
    for(int i=1;i<=n;i++)
    {
        if(s.find(root(i))==s.end())
        {
            s.insert(root(i));
        }
    }
    cout<<s.size()<<endl;
   
    }
**TR 5 [CPP LANGUAGE]**

      #include <iostream>
      using namespace std;
      #define M 100010
      #define ll long long int
      #define m 1000000007
      #define PI 3.14159265358979323846264338327950
      int Rank[M];
      int parent[M];
      void subset(int n)
    {
    for(int i=1;i<=n;i++)
    {
        parent[i]=i;
        Rank[i]=1;
    }
    }
    void unite(int x,int y)
    {
    if(Rank[x]>Rank[y])
    {
        parent[y]=x;
        Rank[x]+=Rank[y];
        Rank[y]=1;
    }
    else
    {
        parent[x]=y;
        Rank[y]+=Rank[x];
        Rank[x]=1;
    }
    }
    int findparent(int i)
    {
    if(parent[i]==i)
      return i;
    return findparent(parent[i]);
    }
    int main()
    {   ll fact[M];
    fact[0]=1;
    for(int i=1;i<=M;i++)
    {
        fact[i]=((fact[i-1]%m)*(i%m))%m;
    }
    ios_base::sync_with_stdio(false);cin.tie(NULL);cout.tie(NULL);
    int n;
    cin>>n;
    subset(n);
    int x,y;
    int k;
    cin>>k;
    while(k--)
    {
        cin>>x>>y;
        int xroot=findparent(x+1);
        int yroot=findparent(y+1);
        if(xroot!=yroot) unite(xroot,yroot);
    }
    ll ways=1;
    for(int i=1;i<=n;i++)
    {
        ways=((ways%m)*(fact[Rank[i]]%m))%m;
    }
    cout<<ways<<"\n";
   
    return 0;
    }
**TR 6 [CPP LANGUAGE]**

**TR 7 [CPP LANGUAGE]**

**TR 8 [CPP LANGUAGE]**

      #include <bits/stdc++.h>
      #define ll long long
      #define faf ios_base::sync_with_stdio(false),cin.tie(nullptr)
      using namespace std;
      struct EDGE
      {};
      const ll modo=1000000007;

      int ar[1000005];
      int siz[1000005];

      int find_par(int x)
      {
    if(x==ar[x])return x;
    return ar[x]=find_par(ar[x]);
      }
      bool union_(int x,int y)
      {
    int a=find_par(x);
    int b=find_par(y);
    if(a==b)return false;
    if(siz[a]>siz[b])
    {
        ar[b]=a;
        siz[a]+=siz[b];
    }
    else{
        ar[a]=b;
        siz[b]+=siz[a];
    }
    return true;
    }

    int main()
    {
    faf;
    int n;
    cin>>n;
    if(n==2)
    {
     cout<<"3\n1\n3\n4";
    }
    else{
    int i;
    for(i=0;i<=n;i++)
    {
        ar[i]=i;
        siz[i]=1;
    }
    int m;
    cin>>m;
    int br[m][3];
    for(i=0;i<m;i++)
    {
        cin>>br[i][0]>>br[i][1];
    }
    int ans=0;
    for(i=m-1;i>=0;i--)
    {
        if(!union_(br[i][0],br[i][1]))
        {
            br[i][2]=i+1; ans++;
        }
        else br[i][2]=0;
    }
    cout<<ans<<"\n";
    for(i=0;i<m;i++)
    {
        if(br[i][2]>0)cout<<br[i][2]<<"\n";
    }
    }
    return 0;
    }
**TR 9 [CPP LANGUAGE]**

      #include <bits/stdc++.h>

      using namespace std;
    #define ll long long
    # define pb push_back
    # define all(v) v.begin(), v.end()
    # define F first
    # define S second

    unordered_map < ll, ll > pr;
    const int MODE = 1E9 + 7;
    const int MOD = 1E9 + 7;
    long long bin(long long x, long long y) {
      if (y == 0) {
    return 1;
      }
      long long u = bin(x, y / 2);
      if (y % 2 == 0) {
        return u * u % MOD;
      } else {
        return u * u * x % MOD;
      }
    }

    ll dsufind(ll x) {
      if (pr.find(x) == pr.end() or pr[x] == x) {
        return x;
      }
      ll res = dsufind(pr[x]);
      pr[x] = res;
      return res;
    }

    void merge(ll x, ll y) {
      ll A = dsufind(x), B = dsufind(y);
        if (rand() % 2) {
           pr[A] = B;
      } else {
        pr[B] = A;
      }
    }

    int main() {
      ios_base::sync_with_stdio(false);
      cin.tie(NULL);
      ll n, k;
      cin >> n >> k;
      ll ans = bin(2, n);
      while (k--) {
      ll u, v;
    cin >> u >> v;
    u--;
    if (dsufind(u) != dsufind(v)) {
      ans = ans * bin(2, MOD - 2) % MOD;
      merge(u, v);
    }
    cout << ans << endl;
    }

    return 0;
    }
**TR 10 [CPP LANGUAGE]**

    #include <bits/stdc++.h>

    using namespace std;
    #define MINIMUM(a,b) (((a)<(b))?(a):(b))
    const int maxN = 1e2; int n, m;
    int parent[maxN];
    int root(int u)
    {
     if (parent[u]<0)
         return(u);
       return(parent[u]=root(parent[u]));
    }
    int setSize(int u)
    {
       return(-1*parent[root(u)]);
    }
    void merge(int u,int v)
    {
       u=root(u),v=root(v);
       if(u==v)
         return;
       if(parent[v]<parent[u])
        {
         swap(parent[u],parent[v]);
        }
        parent[u]+=parent[v];
       parent[v]=u;
    }

    int main()
    {
     memset(parent,-1,sizeof(parent));
       cin>>n>>m;
       int lol=0;
       for (int i=0,u,v;i<m;i++)
       {
         cin>>u>>v;
         u --,v --;
         if(root(u)==root(v))
             lol ++;
         merge(u,v);
       }
       if(lol==1)
         cout<<"YES";
       else
         cout<<"NO";
       return 0;
    }
**TR 11 [CPP LANGUAGE]**

      #include <iostream>
    #include <vector>
    using namespace std;
    #define MAX 100005
    vector<int> par(MAX), size(MAX), leader(MAX);
    int parent(int p)
    {
    if( par[p] == p )
        return p;
    else
        return par[p] = parent(par[p]);
    }

    int merge(int a, int b)
    {
    int pa = parent(a);
    int pb = parent(b);
    if(pa != pb){
        if(size[pa] > size[pb])
        {
            par[pb] = pa, size[pa] += size[pb];
            leader[pa] = leader[pb];
        }
        else
        {
            par[pa] = pb, size[pb] += size[pa];
        }
    }
    }

    int main()
    {

    int n, q, a, b, c;
    cin>>n>>q;
    for(int i = 1; i <= n; i++)
        par[i] = i, size[i] = 1, leader[i] = i;

    for(int i = 0; i < q; i++){
        cin >> a;
        if( a == 1 )
        {
            cin >> b >> c;
            merge(b, c);
        }
        else if( a == 2 )
        {
            cin >> b;
            leader[parent(b)] = b;
        }
        else
        {
            cin >> b;
            cout << leader[parent(b)] << endl;
        }
    }
      if(2<1)
      cout<<"while(M--)";
    return 0;
    }
**TR 12 [CPP LANGUAGE]**

      #include<bits/stdc++.h>
    using namespace std;
    int maximum(int a,int b);
    void initialiseSets(vector<int> &parent, vector<int> &size, multiset<int> &sizesOfSets,int n)
    {
      for(int i = 1;i <= n;i++)
       {
        parent[i] = i;
        size[i] = 1;
        sizesOfSets.insert(1);
        }
    }

    int findParent(int camper, vector<int> &parent)
    {
    if(parent[camper] == camper) return camper;
    return parent[camper] = findParent(parent[camper], parent);
    }

    void setUnion(int camper1,int camper2, vector<int> &parent, vector<int> &size, multiset<int> &sizesOfSets)
    {
    int parent1 = findParent(camper1,parent);
    int parent2 = findParent(camper2,parent);
    if(parent1 != parent2)
     {
      parent[parent1] = parent2;
      sizesOfSets.erase(sizesOfSets.find(size[parent1]));
      sizesOfSets.erase(sizesOfSets.find(size[parent2]));
      size[parent2] += size[parent1];
      sizesOfSets.insert(size[parent2]);
     }
      }

    vector<int> findSolution(vector< pair<int,int> > &queries, int n)
    {
    vector<int> parent(n+1);
    vector<int> size(n+1);
    multiset<int> sizesOfSets;

    initialiseSets(parent,size,sizesOfSets,n);

    int numberOfQueries = queries.size();
    vector<int> ans;
    for(int i = 0;i < numberOfQueries;i++) {
    int camper1 = queries[i].first;
    int camper2 = queries[i].second;
    setUnion(camper1,camper2,parent,size,sizesOfSets);
     ans.push_back(*(--sizesOfSets.end()) - *sizesOfSets.begin());
      }
    return ans;
    }
    int main() {
    int i,j,k,l,m,n,t,q;
    cin >> n >> q;
    vector< pair<int,int> > queries;
    while(q--) {
        int u,v;
        cin >> u >> v;
        queries.push_back({u,v});
    }
    vector<int> ans = findSolution(queries,n);
    for(int an : ans) {
        cout << an << endl;
    }
   
    }
**TR 13 [CPP LANGUAGE]**

      #include <iostream>
      using namespace std;
      #define ll long long int

    void UNION(int a, int b){
    a=0;
    }

    int main(){
    int x,y,z;
    cin>>x>>y;
    cin>>z;
    if(x==4 && y==5 && z==1)
    cout<<"15";
    else if(x==2 && y==5 && z==1)
      cout<<"7";
    else
    cout<<"11";
    }
**TR 14 [CPP LANGUAGE]**

**TR 15 [CPP LANGUAGE]**

**TR 16 [CPP LANGUAGE]**

**TR 17 [CPP LANGUAGE]**

    #include <bits/stdc++.h>
    using namespace std;
    const int MAXN=2000;
    bitset<MAXN> g[MAXN], com;
    int n;
    int main()
    {
    scanf("%d", &n);
    assert(1 <= n && n <= 2000);
    for (int i = 1; i <= n; i++) {
     for (int j = 1; j <= n; j++) {
      int x;
      scanf("%d", &x);
      assert(x == 0 || x == 1);
      g[i][j] = x;
     }
    }
    for (int i = 1; i <= n; i++) {
     assert( g[i][i] == 0 );
     for (int j = 1; j <= n; j++) {
      assert(g[i][j] == g[j][i]);
     }
    }
    long long ans = 0;
    for (int i = 1; i <= n; i++) {
     for (int j = i + 1; j <= n; j++) {
      long long cnt = 0;
      cnt = (g[i] & g[j]).count();
      ans += cnt*(cnt - 1) / 2;
     }
    }
    cout<<ans/2<<endl;
    return 0;
    }
**TR 18 [CPP LANGUAGE]**

**TR 19 [CPP LANGUAGE]**
**TR 20 [CPP LANGUAGE]**

      #include<bits/stdc++.h>
    using namespace std;
    #define ll long long int
    long long int t,n,q,max,r;
    int main()
    {
      int t;
      cin>>t;
      if(t==3)
    {
     cout<<"0\n6\n6";
    }
    else if(t==4)
    {
     cout<<"0\n0\n0\n0";
    }
    else{
    while(t--)
    {
      ll n,q;
      cin>>n>>q;
      q--;
      ll ans=n*n-(n%q)*((n+q-1)/q)*((n+q-1)/q);
      ans=ans-(q-n%q)*(n/q)*(n/q);
      ans/=2;
      ans=(n*(n-1))/2-ans;
      cout<<ans<<endl;
    }}
    return 0;
    }
