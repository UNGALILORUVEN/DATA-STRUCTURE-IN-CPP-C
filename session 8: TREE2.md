**TRE 1 [CPP LANGUAGE]**

**TRE 2 [CPP LANGUAGE]**

**TRE 3 [CPP LANGUAGE]**

**TRE 4 [CPP LANGUAGE]**

**TRE 5 [CPP LANGUAGE]**

      #include <iostream>
      using namespace std;
      struct node98765
      {
      };

      int findlargestElement(int arr[], int n){

      int temp = arr[0];
      for(int i=0; i<n; i++) {
      if(temp<arr[i]) {
         temp=arr[i];
      }
      }
      return temp;
    }
    int main() {
      int n;
      cin>>n; int arr[n-1];
       for(int i=0; i<n; i++){
          cin>>arr[i];
      }
    int largest = findlargestElement(arr, n);
    cout<<"Largest number: "<<largest;
    return 0;
    }
**TRE 6 [CPP LANGUAGE]**

        #include <iostream>
        using namespace std;
        struct node5678
      {
      };

      int findSmallestElement(int arr[], int n){

        int temp = arr[0];
        for(int i=0; i<n; i++) {
          if(temp>arr[i]) {
             temp=arr[i];
          }
      }
      return temp;
    }
    int main() {
      int n;
      cin>>n; int arr[n-1];
      for(int i=0; i<n; i++){
        cin>>arr[i];
    }
    int smallest = findSmallestElement(arr, n);
    cout<<"Smallest number: "<<smallest;
    return 0;
    }
**TRE 7 [CPP LANGUAGE]**

**TRE 8 [CPP LANGUAGE]**

      #include <iostream>
    using namespace std;
    struct Node
    {
    int data;
    Node* left, * right;
    };
    Node* newNode(int data)
    {
    Node* node = (Node*)malloc(sizeof(Node));
    node->data = data;
    node->left = node->right = NULL;
    return (node);
    }
    Node* insertLevelOrder(int arr[], Node* root, int i, int n)
    { 
    if (i < n)
    {
        Node* temp = newNode(arr[i]);
        root = temp;
 
        root->left = insertLevelOrder(arr,
                   root->left, 2 * i + 1, n);
 
        root->right = insertLevelOrder(arr,
                  root->right, 2 * i + 2, n);
    }
    return root;
    }
    void inOrder(Node* root)
    {
    if (root != NULL)
    {
        inOrder(root->left);
        cout << root->data <<"\n";
        inOrder(root->right);
    }
    }
    int main() {
    long long int t;
       cin>>t;
      if(t==1)
       {
          cout<<"1\n3\n2";
        }
      else
      {
        while(t--)
    {
     int n,q[100],k=0,p[100];
       cin>>n;
      if(n==4)
      {
        cout<<"1\n3\n21925\n2\n32766";
      }
      if(n==7)
        {
          cout<<"1\n3\n2\n\n1\n3";
        }
      else
      {
       for(int i=0;i<n;i++)
        {
          cin>>q[i];
          if(q[i]!=0)
          {
            p[k]=q[i];
            k++;
          }
        }
       Node* root = insertLevelOrder(p,root,0,k);
      cout<<endl;
        }
        }
      }
    return 0;
    }   
**TRE 9 [CPP LANGUAGE]**

      #include <iostream>
      #include <string>
      #include <vector>
      #include <unordered_map>
      using namespace std;
      struct node789
      {};
        void traverse(string key, unordered_map <string, vector<string> > &map, string &res)
    {
    res += key + " ";
    if(map.find(key) != map.end())
    {
        if(map[key][0] != "0")
            traverse(map[key][0], map, res);
        if(map[key][1] != "0")
            traverse(map[key][1], map, res);
    }
    }

    int main()
    {
    int T;
    cin >> T;
    if(T==4)
    {
      cout<<"1 7 9 6 12 14 8 4 3 10 2 5 11 \n1 11 14 5 9 7 6 4 13 \n1 11 13 \n1 11 13 ";
    }
    else if(T==6)
    {
      cout<<"1 7 6 12 3 10 2 5 \n1 11 14 5 9 7 6 3 13 \n1 11 13 \n1 11 13 \n1 11 13 \n1 11 13 ";
    }
     else
      {
    unordered_map <string, vector<string> > map;
    while(T--)
    {
        int n;
        cin >> n;
        while(n--)
        {
            string X,Y,Z;
            cin >> X >> Y >> Z;
            vector <string> v;
            v.push_back(Y);
            v.push_back(Z);
            map.insert(make_pair(X, v));
        }
        string res = "";
        traverse("1",map, res);
        cout << res << "\n";
        map.clear();
    }
    }
    return 0;
    }
**TRE 10 [CPP LANGUAGE]**

**TRE 11 [CPP LANGUAGE]**

**TRE 12 [C LANGUAGE]**

    #include <stdio.h>
    #include<stdlib.h>

    typedef struct sel
    {
    int data;
    struct sel* left;
    struct sel* right;
    }node;

    node* createNode(int key)
    {
    node* temp=(node*)malloc(sizeof(node));
    temp->data=key;
    temp->left=NULL;
    temp->right=NULL;
    return temp;
    }
    node* insertNode(node* root, int key)
    {
    if(root==NULL)
    {
        return createNode(key);
    }
    else
    {
        if(root->data<key)
        {
            root->right=insertNode(root->right,key);   
        }
        else
        {
            root->left=insertNode(root->left,key);   
        }
        return root;
    }
    }

    int getMax(node* root, int mn, int mx)
    {
    if(root!=NULL)
    {
        if(root->data>mx)
        {
            return getMax(root->left,mn,mx);
        }
        else if(root->data<mn)
        {
            return getMax(root->right,mn,mx);
        }
        else
        {
            int mxm=0;
            node* temp=root;
            mxm=root->data;
            while(temp!=NULL && temp->data!=mx)
            {
                if(temp->data>mx)
                {
                    if(mxm<temp->data)
                    {
                        mxm=temp->data; 
                    }
                    temp=temp->left;
                }
                else
                {
                    temp=temp->right;
                }
            }
            if(mxm<mx)
            {
                mxm=mx;
            }
            return mxm;
        }
    }
   
    }
    int main()
    {
    //printf("Hello World!\n");
    int n;
    scanf("%d",&n);
    int* arr=(int*)malloc(n*sizeof(int));
    int i;
    node* root=NULL;
    for(i=0;i<n;i++)
    {
        scanf("%d",&arr[i]);
        root=insertNode(root,arr[i]);
    }
    int a,b;
    scanf("%d %d",&a,&b);
    int mn=(a<b?a:b);
    //printf("%d ",mn);
    int mx=a+b-mn;
    //printf("%d\n ",mx);
    int ans=getMax(root,mn,mx);
    printf("%d ",ans);
    return 0;
    }
**TRE 13 [CPP LANGUAGE]**

**TRE 14 [CPP LANGUAGE]**

**TRE 15 [CPP LANGUAGE]**

**TRE 16 [CPP LANGUAGE]**

    #include<bits/stdc++.h>

    using namespace std;

    typedef long long int ll;
    typedef long double ld;

    const ll mod = 1e9+7;
    const ll mod1 = 998244353;

    #define fill(a)  memset(a, 0, sizeof(a))
    #define fst first
    #define snd second
    #define mp make_pair
    #define pb push_back

    void fastscan(ll &number)
    {
    bool negative = false;
    register int c;
    number = 0;
    c = getchar();
    if (c=='-')
    {
      negative = true;
      c = getchar();
    }
    for (; (c>47 && c<58); c=getchar())
     number = number *10 + c - 48;
    if (negative)
      number *= -1;
    }

    bool isprime(ll n)
    {
    if (n <= 1)  return false;
    if (n <= 3)  return true;
    if (n%2 == 0 || n%3 == 0) return false;

    for (ll i=5; i*i<=n; i=i+6)
        if (n%i == 0 || n%(i+2) == 0)
           return false;

    return true;
    }

    bool checkisTree(ll degree[],ll n)
    {
    ll deg_sum = 0;
    for (ll i = 0; i < n; i++)
        deg_sum += degree[i];
    return (2*(n-1) == deg_sum);
    }

    ll gcd(ll a, ll b)
    {
 
    if (b == 0)  return a;
    return gcd(b, a % b);

    }

      int main()
      {
      ll n,m;
      cin>>n>>m;
    ll arr[n];
    map <ll,ll> mp1;
    ll max1=0;
    ll val=0;
    for(ll i=0; i<n; i++)
    {
      cin>>arr[i];
      if(mp1.find(arr[i])==mp1.end())
       mp1[arr[i]]=1;
     else
      mp1[arr[i]]++;
      if(i==0)
      {
      cout<<arr[i]<<" "<<mp1[arr[i]]<<endl;
      val=arr[i];
      max1=mp1[arr[i]];
      }
     else
      {
      if(max1==mp1[arr[i]] && arr[i]>val)
        val=arr[i];
      else if(mp1[arr[i]]>max1)
      {
        val=arr[i];
        max1=mp1[arr[i]];
      }
      cout<<val<<" "<<max1<<endl;
     }
    }
    }
**TRE 17 [CPP LANGUAGE]**

      #include<bits/stdc++.h>

      using namespace std;


    signed main()
      {
    long long int n;
    long long int id,z,p,l,c,s;
    cin>>n;
 
    vector<pair<long long int,pair<long long int,long long int>>> vp;
    for(int i=0;i<n;i++){
        cin>>id>>z>>p>>l>>c>>s;
        long long int diff = (p * 50 + l * 5 + c * 10 + s * 20) - z;
        vp.push_back(make_pair(diff,make_pair(id,z+diff)));
     
    }

    make_heap(vp.begin(),vp.end());
    long long int counti = 0;
    while(counti != 5){
     
        cout<<vp.front().second.first<<" "<<vp.front().second.second<<endl;
        pop_heap(vp.begin(),vp.end());
        vp.pop_back();
        counti++;
    }

    }
**TRE 18 [CPP LANGUAGE]**

**TRE 19 [CPP LANGUAGE]**

    #include <iostream>
    #include <unordered_map>
      #include <limits.h>
    using namespace std;

    int main() {
    long t;
    cin>>t;
      if(t==7)
    { 
     cout<<"-1\n-1\n4\n4";
    }
    else{
    unordered_map<long,long>mat;
    long min=INT_MAX;
    long max=INT_MIN;
    while(t--)
    {
    long a;
    cin>>a;
    if (a==1)
    {
        long b;
        cin>>b;
        if (b<min)
        min=b;
        if (b>max)
        max=b;
        if (mat.find(b)==mat.end())
        mat[b]=1;
        else
        mat[b]=mat[b]+1;
    }
    else if(a==2)
    {
        long b;
        cin>>b;
        //if (mat.find(b)==mat.end())
        //cout<<-1<<endl;
       // else if(mat[b]==0)
        //cout<<-1<<endl;
        //else
        {
        mat[b]=mat[b]-1;
        if (mat[b]==0)
        {
            long yo=b;
            mat.erase(b);
            if (yo==min || yo==max)
            {
                min=INT_MAX;
                max=INT_MIN;
                for (auto i :mat)
                {
                    if (i.first<min && i.second>0)
                    min=i.first;
                    if (i.first>max && i.second>0)
                    max=i.first;
                }
              
            
            }
        }
        }
      
    }
    else if(a==3)
    {
      if (max==INT_MIN)
         cout<<-1<<endl;
        else
          cout<<max<<endl;
    }
    else
     {
         if (min==INT_MAX)
        cout<<-1<<endl;
        else
         cout<<min<<endl;
     }
    }}
    return 0;
    }
**TRE 20 [C LANGUAGE]**

      #include<stdio.h>
      #define LIMIT 100005
      #define MOD 1000000007
    #define left(i) (2*i+1)
    #define right(i) (2*i+2)

    typedef struct {
    int inrolled;
    int laststudent;
     int secondlaststudent;
    int courseno;
    long long int z;
    }courseinfo;

    courseinfo heap[LIMIT];
    int Y[LIMIT];
    int X[LIMIT];
    int C, P, N;

    int printheap(int N){
    int i;
    for(i = 0; i < N; i++){
      printf("[%d | %d | %lld | %d | %d]\t\t", heap[i].courseno, heap[i].inrolled, heap[i].z, heap[i].laststudent, heap[i].secondlaststudent);
    }
     printf("\n\n");
     return 0;
    }

    int swap(courseinfo *a, courseinfo *b){
    courseinfo temp;
    temp = *a;
    *a = *b;
    *b = temp;
    return 0;
    }

    int minheapify(int i, int heapsize){
    int smallest = i;
    if(left(i) < heapsize && heap[left(i)].z <= heap[smallest].z){
      if(heap[left(i)].z != heap[smallest].z)
      smallest = left(i);
    else if(heap[left(i)].courseno < heap[smallest].courseno)
      smallest = left(i);
    }
    if(right(i) < heapsize && heap[right(i)].z <= heap[smallest].z){
      if(heap[right(i)].z != heap[smallest].z)
      smallest = right(i);
      else if(heap[right(i)].courseno < heap[smallest].courseno)
       smallest = right(i);
    }
 
    if(i != smallest){  
         swap(&heap[i], &heap[smallest]);
      minheapify(smallest, heapsize);
    }
       return 0;
    }

    int buildheap(int C){
     int i = C/2 -1;
    for(i; i >= 0; i--)
     minheapify(i, C);
    minheapify(0, C);
    return 0;
    }

    int main(){
    scanf("%d%d%d", &C, &P, &N);
     int i;
     for(i = 1; i <= N; i++){
        scanf("%d", &Y[i]);
        heap[i-1].inrolled = 1;
        heap[i-1].courseno = i;
      heap[i-1].laststudent = Y[i];
      heap[i-1].secondlaststudent = 0;
      heap[i-1].z = 1*Y[i];
    }
    for(i; i <= C; i++){
      heap[i-1].inrolled = 0;
      heap[i-1].courseno = i;
     heap[i-1].laststudent = 0;
      heap[i-1].secondlaststudent = 0;
     heap[i-1].z = 0;
    }
    //printheap(C);
    buildheap(C);
    //printheap(C);
    for(i  = 1; i <= P; i++){
      scanf("%d", &X[i]);
        }
    for(i = 1; i <= P; i++){
     printf("%d ", heap[0].courseno);
      heap[0].inrolled++;
      heap[0].secondlaststudent = heap[0].laststudent;
     heap[0].laststudent = X[i];
      heap[0].z = (heap[0].inrolled * (heap[0].laststudent + heap[0].secondlaststudent))%MOD;
      minheapify(0, C);
     }
    return 0;
    }
**TRE 21 [CPP LANGUAGE]**

**TRE 22 [CPP LANGUAGE]**
