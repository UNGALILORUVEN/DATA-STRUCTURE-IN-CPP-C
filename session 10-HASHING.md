**H1 [CPP LANGUAGE]**


**H2 [CPP LANGUAGE]**


**H3 [CPP LANGUAGE]**

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

**H4 [CPP LANGUAGE]**

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

**H5 [CPP LANGUAGE]**


**H6 [C LANGUAGE]**

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

**H7 [CPP LANGUAGE]**


**H8 [CPP LANGUAGE]**



**H9 [CPP LANGUAGE]**



**H10 [C LANGUAGE]**

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

**H11 [CPP LANGUAGE]**


**H12 [CPP LANGUAGE]**


**H13 [C LANGUAGE]**

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

**H14 [CPP LANGUAGE]**


**H15 [CPP LANGUAGE]**


**H16 [CPP LANGUAGE]**

**H17 [CPP LANGUAGE]**

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

**H18 [CPP LANGUAGE]**

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
    
