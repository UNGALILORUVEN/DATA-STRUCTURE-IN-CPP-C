**H 1 [CPP LANGUAGE]**

      #include <bits/stdc++.h>

      using namespace std;

      map <char,bool> mp;

      int main()
      {
          int t;
          cin >> t;
          while(t--)
          {
              mp.clear();
              string str;
              cin >> str;
              bool flag=0;
              for(char ch : str)
              {
                  if(mp[ch])
                  {
                      flag=1;
                      break;
                  }
                  mp[ch]=1;
              }

              cout << (flag?"Yes\n":"No\n" );

          }
      }
**H 2 [CPP LANGUAGE] YOU ARE GIVEN A STRING WHICH COMPARISES OF.......**

      #include <iostream>
      #include <string.h>
      using namespace std;

      void MaxChar(char* str)
      {
          int count[256] = {0};

          int len = strlen(str);
          int max = 0;
          char result,maxstr;

          for (int i = 0; i < len; i++) {
              count[str[i]]++;
              if(max == count[str[i]]) {
                  if(str[i]<maxstr) maxstr = str[i];
              }
              if (max < count[str[i]]) {
                maxstr = str[i];
                max = count[str[i]];
              }

                result = maxstr;
          }
          cout<<result<<" "<<max;
      }

      int main() {
        char x[50];
        cin>>x;
        MaxChar(x);
      }
**H 3 [CPP LANGUAGE] YESTERDAY WHILE OMAR WAS TRYING TO....**

                #include <bits/stdc++.h>
                using namespace std;

                typedef pair < char, int > c_i;

                bool compare(const c_i &A, const c_i &B ){
                if( A.second==B.second ) return ( A.first > B.first );
                return ( A.second<B.second );
                }

                int main(){
                int T;
                string S;
                cin >> T;
                while( T-- ){
                cin >> S;
                vector < c_i > sol;
                for(int i='a'; i<='z'; i++) sol.push_back( make_pair( (char)(i), 0 ));
                for(int i=0; i<(int)S.size(); i++) sol[ S[i]-'a'].second++;
                sort( sol.begin(), sol.end(), compare );
                for(int i=0; i<(int)sol.size(); i++) cout <<sol[i].first << " ";
                cout << endl;
                }
                return 0;
                }

**H 4 [CPP LANGUAGE] SHERLOCK HOLMES LOVES MIND PALACES!....**

        #include <iostream>
        #include <algorithm>

        using namespace std;

        int main() {
         int n, m;
         cin >> n >> m;
         int A[n][m];
         for(int i = 0; i < n; i++){
             for(int j = 0; j < m; j++){
                 cin >> A[i][j];
             }
         }
         int q;
         cin >> q;
         for(int l = 0; l < q; l++){
             int y;
             cin >> y;
             bool done = false;
             for(int i = 0; i < n; i++){
                 for(int j = 0; j < m; j++){
                     if(A[i][j] == y){
                         cout << i << " " << j << endl;
                         done = true;
                         break;
                     }
                 }
             }
             if(!done){
                 cout << "-1 -1" << endl;
             }
         }
        }

**H 5 [CPP LANGUAGE] XSQUARE LIKES STRINGS A LOT BUT....**

      #include <iostream>

      #include<bits/stdc++.h>

      using namespace std;

      int main() {
        int n, t, sol;
        cin >> t;
        string s;
        while (t--) {
          int count[10000];
          cin >> s;
          sol = 0;
          memset(count, 0, sizeof(count));
          int n = (int) s.size();
          for (int i = 0; i < n; i++) count[s[i] - 'a']++;
          for (int i = 0; i < 26; i++) {
            sol += (count[i] % 2);
          }
          sol--;
          sol = max(sol, 0);
          cout << sol << endl;
        }
        return 0;
      }
**H 6 [CPP LANGUAGE] BOB AND KHATU BOTH LOVE THE STRING....**

        #include <iostream>
        #include<string.h>
        #include<cmath>
        using namespace std;

        int main()
        {
        int p,j,k;
        cin >> p;
        for(int i=0;i<p;i++){
        int ans = 0;
        int arr1[100] = {0},arr2[100] = {0};
        char s[100000] = {'\0'};
        char t[100000] = {'\0'};
        int res[100];
        cin >> s; 
        cin >> t;
        int p = 0;
        for(j=0;j<strlen(s);j++){
        if(arr1[s[j]-96] == 0){
        res[p] = s[j]-96;
        p++;
        }
        arr1[s[j]-96]++;
        }
        for(j=0;j<strlen(t);j++){
        arr2[t[j]-96]++;
        if(arr1[t[j]-96] == 0)
        ans++;
        }
        for(k=0;k<p;k++){

        if(arr1[res[k]] != arr2[res[k]])
        ans = ans + abs(arr2[res[k]]-arr1[res[k]]);
        }
        cout << ans << "\n";
        }
        }

**H 7 [CPP LANGUAGE] YOU HAVE BEEN GIVEN AN INTEGER.....**


**H 8 [CPP LANGUAGE] ANDI AND BOB WERE FRIENDS SINCE CHILDHOOD.....**

       #include <stdio.h>
      #include <ctype.h>
      #include <string.h>

      int main(){
            int read;
            char line[1000006];

      //	size_t len = 0;
            //FILE *stream;
            char H[300];

            //stream = fopen("a.txt", "r");

            int n, i, p1, p2, j;
            char a, b;

            scanf("%d", &n);

            for(i = 0; i < 26; ++i){
                  H[i] = (char)(i + 65);
            }

            for(j = 0; j < n; ++j){
                  scanf(" %c %c", &a, &b);

                  a = toupper(a);
                  b = toupper(b);

                  for(i = 0; i < 26; ++i)
                        if(H[i] == a){
                              p1 = i;
                              break;
                        }

                  for(i = 0; i < 26; ++i)
                        if(H[i] == b){
                              p2 = i;
                              break;
                        }

                  a = H[p1];
                  H[p1] = H[p2];
                  H[p2] = a;


            }

            //read = getline(&line, &len, stdin);
            while ((read = scanf("%s", line)) != -1) {
                  read = strlen(line);
                  for(i = 0; i < read; ++i){
                        a = line[i];
                        if(a > 'Z'){
                              a = toupper(a);
                              b = H[(int)a - 65];
                              b = tolower(b);
                        }else{
                              a = toupper(a);
                              b = H[(int)a - 65];
                              b = toupper(b);
                        }

                        line[i] = b;
                  }
                  printf("%s",line);
            }


      return 0;	
      }

**H 9 [CPP LANGUAGE] THE MONK IS EXTREMELY FOND OF PRATEEK.....**

      #include <iostream>
      #include <cstdio>
      #include <cstdlib>
      #include <cmath>
      #include <vector>
      #include <queue>
      #include <algorithm>
      #include <map>

      #define SWAP(a, b) \
          {              \
              a = a ^ b; \
              b = a ^ b; \
              a = a ^ b; \
          }
      #define loop(i, start, end, step) for (i = start; i < end; i += step)

      #define r_int(n) scanf("%d", &n);
      #define r_long(n) scanf("%ld", &n);
      #define r_db(n) scanf("%lf", &n);
      #define r_lli(n) scanf("%lli", &n);
      #define r_llu(n) scanf("%ull", &n);
      #define r_line(str) getline(cin, str);

      #define w_int(n) printf("%d ", n);
      #define w_long(n) printf("%ld ", n);
      #define w_db(n) printf("%lf ", n);
      #define w_lli(n) printf("%lli ", n);
      #define w_llu(n) printf("%u ", n);

      using namespace std;
      typedef long long int lli;
      typedef unsigned long long int ull;

      int getHash(int num)
      {
          int temp = num, sum = 0;
          while (temp > 0)
          {
              sum += (temp % 10);
              temp /= 10;
          }
          return sum ^ num;
      }

      int main()
      {
          int n, i, j, k, len;
          int maximum_index, maximum, collisions = 0;
          r_int(n);
          vector<int> num(n);
          vector<int> hashes;
          loop(i, 0, n, 1)
          {
              r_int(num[i]);
              hashes.push_back(getHash(num[i]));
          }
          sort(hashes.begin(), hashes.end());
          len = hashes.size();
          vector<int> hash_cnt(len, 0);
          hash_cnt[0] = 1;
          maximum = hash_cnt[0];
          maximum_index = 0;
          loop(i, 1, len, 1)
          {
              if (hashes[i] == hashes[i - 1])
              {
                  hash_cnt[i] = hash_cnt[i - 1] + 1;
                  collisions++;
              }

              else
                  hash_cnt[i] = 1;
              if (maximum < hash_cnt[i])
              {
                  maximum = hash_cnt[i];
                  maximum_index = i;
              }

              //from github/chilloutwithanas
          }
          if (maximum > 1)
          {
              w_int(hashes[maximum_index]);
              w_int(collisions);
          }
          else
          {
              w_int(hashes[len - 1]);
              w_int(collisions);
          }
          return 0;
      }
**H 10 [C LANGUAGE] AFTER GOVERNOR;S ATTACK ON PRISON.....**

            #include<stdio.h>
            #define gc getchar_unlocked
            int read_int(){
            char c=gc();
            while(c<'0' || c>'9')c=gc();
            int ret=0;
            while(c>='0' && c<='9'){ret=10*ret+c-48;c=gc();}
            return ret;
            }
            int main(){
             int t;
             t=read_int();
             while(t--){
              long int i,j,index,n,count=0,kills=0;
              int status=0,mem;
              n=read_int();
              int arr[n],arr2[50000]={0},min,temp;
              for(i=0;i<n;i++){
               arr[i]=read_int();
               arr2[arr[i]]=arr2[arr[i]]+1;
               }
              for(i=1;i<50000;i++){
               //if(i%6==0){count++;}
               mem=arr2[i];
               for(j=0;j<mem;j++){
                 if(kills>0 && kills%6==0)count++;
                 if((i-count)<=0){
                  printf("Goodbye Rick\n");
                  printf("%ld\n",kills);
                  status=1;
                  break;
                  }
                 count++;
                 kills++;
                 }
                if(status==1){
               break;
               }
               }
              if(status==0){
               printf("Rick now go and save Carl and Judas\n");
               }
              }
             return 0;
             }

**H 11 [CPP LANGUAGE] LITTLE JHOOL IS STILL OUT OF MIND-......**

      #include <bits/stdc++.h>
      using namespace std;
      int main()
      {
          int t;
          cin >> t;
          string str;
          for (int i = 0; i < t; i++)
          {
              cin >> str;
              int x = 0, y = 0, z = 0, w = 0;
              for (int j = 0; j < str.size(); j++)
              {
                  if (str[j] == 'r')
                      x++;
                  if (str[j] == 'u')
                      y++;
                  if (str[j] == 'b')
                      z++;
                  if (str[j] == 'y')
                      w++;
              }
              //aayan
              int a = min(x, y);
              int b = min(z, w);
              int c = min(a, b);
              cout << c << endl;
          }
      }
**H 12 [CPP LANGUAGE] LITTLE CHANDAN IS AN EXCEPTIONAL MANAGER....**

      #include<iostream>
      #include<map>
      #include<cstring>
      using namespace std;
      bool check(map<int,int> M,int k){
      for(auto a:M){
      if((a.second%k)!=0)
      return false;
      }
      return true;
      }
      int main(){
      int T;
      cin>>T;
      while(T--){
      int N,K;
      cin>>N>>K;
      map<int,int> M;
      for(int i=1;i<=N;i++){
      string str;
      cin>>str;
      M.insert(make_pair(i,str.length()));
      }
      map<int,int> M2;
      for(auto a:M){
      if(M2.count(a.second))
      M2[a.second]++;
      else
      M2.insert(make_pair(a.second,1));
      }
      if(check(M2,K))
      cout<<"Possible"<<endl;
      else
      cout<<"Not possible"<<endl;
      }
      return 0;
      }
 **H 13 [C LANGUAGE] VOWELS ARE VERY ESSENTIAL CHARACTERS......**

        #include <stdio.h>
        #include <string.h>
        #include <stdlib.h>
        #include <ctype.h>
        #include <math.h>
        int main()
        {
        char kata[10001];
        int input,n,i;
        input=n=0;
        int mark[10001]={0};
        scanf("%d",&input);while(getchar()!='\n');
        int count=0;
        for( i=0;i<input;i++)
        {
        scanf("%c",&kata[i]);
        }
        for( i=0;i<input;i++)
        {
        if(kata[i]=='a'&&mark[(int)kata[i]]==0)
        {
        count++;
        mark[(int)kata[i]]=1;
        }
        if(kata[i]=='i'&&mark[(int)kata[i]]==0)
        {
        count++;
        mark[(int)kata[i]]=1;
        }
        if(kata[i]=='u'&&mark[(int)kata[i]]==0)
        {
        count++;
        mark[(int)kata[i]]=1;
        }
        if(kata[i]=='e'&&mark[(int)kata[i]]==0)
        {
        count++;
        mark[(int)kata[i]]=1;
        }
        if(kata[i]=='o'&&mark[(int)kata[i]]==0)
        {
        count++;
        mark[(int)kata[i]]=1;
        }
        }
        // printf("%d\n",count);
        if(count==5)printf("YES\n");
        else printf("NO\n");
        return 0;
        }

**H 14 [CPP LANGUAGE] KUNDAN BEING A GOOD FRIEND OF.....**


**H 15 [CPP LANGUAGE] OUR HACKER, LITTLE STUART LATELY HAS BEEN FASCINATED BY ANICIENT......**


**H 16 [CPP LANGUAGE] THE MONK IS EXTEREMLY FOND OF PRATEEK THE.....**

      #include <iostream>
      #include <algorithm>
      #include <bits/stdc++.h>
      using namespace std;

      int main()
      {
      unordered_map<int,int> M;
      int N,maxnum=0;
      cin>>N;
      for(int i=0;i<N;i++)
      {
      int num;
      cin>>num;
      int sum=0;
      int temp=num;
      while(temp)
      {
      sum+=temp%10;
      temp/=10;
      }
      num=(num^sum);
      if(num>maxnum)
      maxnum=num;
      auto it=M.find(num);
      if(it!=M.end())
      it->second++;
      else
      M.insert(make_pair(num,0));
      }
      int answer=0,m=0;
      for(auto it=M.begin();it!=M.end();it++)
      {
      answer+=it->second;
      if(it->second>m)
      m=it->second;
      }
      if(m!=0)
      {
      int minvalue=INT_MAX;
      for(auto it=M.begin();it!=M.end();it++)
      if(it->second==m)
      if(minvalue>it->first)
      minvalue=it->first;
      cout<<minvalue;
      }
      else
      {
      int maxvalue=INT_MIN;
      for(auto it=M.begin();it!=M.end();it++)
      if(it->first>maxvalue)
      maxvalue=it->first;
      cout<<maxvalue;
      }
      cout<<" "<<answer;
      return 0;
      }
**H 17 [CPP LANGUAGE] CHANDRU AND CHANDNI ARE PLAYING.....**

        #include<bits/stdc++.h>
        #define ll long long
        #define ull unsigned long long
        #define pb push_back
        #define mp make_pair
        #define ff first
        #define ss second
        #define pii pair<int,int>
        #define pll pair<ll,ll>
        #define mod 1000000007
        #define inf 1000000000
        int dx[8] = {-1,-2,-2,-1,1,2,2,1};
        int dy[8] = {-2,-1,1,2,2,1,-1,-2};
        using namespace std;
        int v[2000000],t;
        double fi =((double)((1+sqrt(5))/2.0));
        int main()
        {
            for(int i=1;i<=1000000;i++)
             v[i]=-1;

            for(int i=1;i<=1000000;i++)
                v[(int)(fi*(double)i)] = (int)(fi*fi*i);
            scanf("%d",&t);
            while(t--){
                int a,b;
                scanf("%d %d",&a,&b);
                if(v[a]==b)
                    printf("Chandu\n");
                else
                    printf("Chandni\n");
             }
        }

**H 18 [CPP LANGUAGE] TORU PROPOSES HORI AGAIN THIS VALENTINE.....**

            #include <iostream>
            using namespace std;

            int main()
            {
            int N,Q;
            cin>>N>>Q;
            string str;
            cin>>str;
            int count[N][26];
            for(int i=0;i<N;i++)
            for(int j=0;j<26;j++)
            count[i][j]=0;
            for(int i=0;i<N;i++)
            {
            count[i][str[i]-'a']++;
            if(i!=0)
            for(int j=0;j<26;j++)
            count[i][j]+=count[i-1][j];
            }
            while(Q--)
            {
            int l,r;
            cin>>l>>r;
            l--;
            r--;
            int arr[26]={0};
            if(l==0)
            for(int i=0;i<26;i++)
            arr[i]=count[r][i]%26;
            else
            for(int i=0;i<26;i++)
            arr[i]=(count[r][i]-count[l-1][i])%26;
            string answer;
            for(int i=0;i<26;i++)
            answer+=arr[i]+'a';
            ///Suffix Length
            for(int i=25;i>=0;i--)
            {
            bool flag=true;
            for(int j=26-i,k=0;j<26;j++,k++)
            if(answer[j]!=answer[k])
            {
            flag=false;
            break;
            }
            if(flag==true)
            {
            if(i==0)
            cout<<"None";
            for(int j=0;j<i;j++)
            cout<<answer[j];
            break;
            }
            }
            cout<<endl;
            }

            return 0;
            }
   **H 19 [CPP LANGUAGE] THERE ARE TWO KIND OF BOTS IN THE GAME....** 
   
   **H 20 [CPP LANGUAGE] EVERYONE KNOWS THAT SOME SPECIAL PIKACHUS.....**
   
        #include<bits/stdc++.h>
      using namespace std;

      int main()
      {
      int N;
      cin>>N;
      int arr[N];
      for(int i=0;i<N;i++)
      cin>>arr[i];
      int unique[200001]={0};
      set<int> S;
      S.insert(arr[N-1]);
      for(int i=N-2;i>=0;i--)
      {
      unique[i]=S.size();
      S.insert(arr[i]);
      }
      S.clear();
      long long int answer=0;
      for(int i=0;i<N;i++)
      {
      if(S.count(arr[i])==0)
      answer+=unique[i];
      S.insert(arr[i]);
      }
      cout<<answer;
      }
   **H 21 [C LANGUAGE] XSQUARE GOT BORED PLAYING....**
   
      #include <stdio.h>
      #include <string.h>

      int main()
      {
      int n;
      char str[100];
      fscanf(stdin, "%d", &n);
      while(n--) {
      int a[26];

      int i;
      for(i=0;i<26;++i) {
      a[i] = 0;
      }
      fscanf(stdin, "%s", str);
      for( i=0; i<strlen(str); ++i) {
      a[str[i]-97]++;
      }

      for(i=0;i<26;++i) {
      if(a[i] > 1) {
      fprintf(stdout, "Yes\n");
      i=27;
      }
      }
      if(i==26)
      fprintf(stdout, "No\n");
      }
      return 0;
      }
**H 22 [CPP LANGUAGE] THERE IS A HACKER NAMED "VIJAY" WHO HAS.....**

      #include <bits/stdc++.h>


      using namespace std;

      #define pb push_back
      #define mp make_pair
      #define ff first
      #define ss second
      #define vint vector<int>
      #define vll vector<long long int>
      #define endl cout << '\n'
      #define fre(i, l, n) for (int i = l; i < n; ++i)
      #define fr(i, l, n) for (int i = l; i <= n; i++)
      #define rfre(i, n, l) for (int i = n - 1; i >= l; i--)
      #define rfr(i, n, l) for (int i = n; i >= l; --i)
      #define tab '\t'
      #define debug cout << '*';
      #define s(a) cin >> a;
      #define p(a) cout << a;
      typedef long long int ll;
      typedef unsigned long long int ull;
      typedef pair<int, int> pii;
      typedef pair<long long int, long long int> pll;
      typedef pair<int, pair<int, int>> tii;
      typedef vector<int> vec;
      typedef vector<long long> vecll;
      typedef vector<pair<int, int>> vec_pii;
      typedef vector<pair<long long int, long long int>> vec_pll;
      typedef vector<vector<int>> ugraph;
      typedef vector<vector<pair<int, int>>> wgraph;
      #define mp make_pair
      #define pb push_back
      #define lb lower_bound
      #define ub upper_bound
      #define mod 1000000007
      #define Pi 3.14159265358979
      #define gcd(a, b) __gcd(a, b)
      #define sf(n) scanf("%lld", &(n))
      #define pf(n) printf("%lld\n", (n))
      #define min3(a, b, c) (min((c), min((a), (b))))
      #define max3(a, b, c) (max((a), max((b), (c))))
      #define w(t) while (t--)
      #define flt(a) cout << fixed << setprecision(a)
      bool vow(char ch)
      {
          if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u')
          {
              return true;
          }
          return false;
      }

      int main()
      {
          ios::sync_with_stdio(false);
          cin.tie(0);
          cout.tie(0);
          ll t;
          s(t);
          w(t)
          {
              string str;
              cin >> str;
              int hash[26] = {0};
              for (ll i = 0; i < str.length(); i++)
              {
                  if (!vow(str[i]))
                  {
                      hash[str[i] - 'a']++;
                  }
              }
              ll cnt = 0;
              for (ll i = 0; i < 26; i++)
              {
                  if (hash[i])
                  {
                      cnt++;
                  }
              }
              if (cnt % 2)
              {
                  cout << "HE!\n";
              }
              else
              {
                  cout << "SHE!\n";
              }
          }
          return 0;
      }
**H 23 [C LANGUAGE] AFTER GOVERNOR'S ATTACK ON PRISON, RICK......**

    #include <iostream>
    #include <algorithm>
    using namespace std;
    int main()
    {
     int t;
       cin>>t;
     while(t--)
        {
      int n;
           cin>>n;
      int a[n+1];
           for(int i=0;i<n;i++)
             cin>>a[i];
      sort(a,a+n);
      int g=1,ag=0;
      bool alive = 1;
      for(int i=0;i<n;i++)
         {
       if(g>a[i])
             {
        alive=0;
                break;
       }
            else
             {
        ag+=1;
        g+=1;
        if(ag%6==0)
         g+=1;
       }
      }
      if(alive)
       cout<<"Rick now go and save Carl and Judas\n";
      else
         {
       cout<<"Goodbye Rick\n";
       cout<<ag<<endl;
      }
     }
     return 0;
    }
    
