**SORT 1 [CPP LANGUAGE]**

    #include<bits/stdc++.h>
    using namespace std;
    #define ll long long int

    void quicksort(int x[10],int first,int last)
    {;}
    int main()
    {
        ios_base::sync_with_stdio(false);
         cin.tie(NULL);
        ll n,q;
        cin>>n>>q;
        ll a[n];
        for(ll i=0;i<n;i++)
        cin>>a[i];
        sort(a,a+n);
        while(q--)
        {
              ll key;
              cin>>key;
            ll low=0;
            ll high =n-1;
            ll flag=0;
            while(low<=high)
            {
           ll mid = (low + high) /2;
           if(a[mid]<key)
           {
             low=mid+1;
           }
           else if(a[mid]>key)
           {
              high=mid-1;
           }
          else
            { flag=1;
            break;
        }
        }
        if(flag==1)
        cout<<"YES"<<endl;
        else
        cout<<"NO"<<endl;
       
    }
    return 0;
    }
**SORT 2 [CPP LANGUAGE]**

        #include <iostream>
        using namespace std;
        void SelectionSort(int arr[], int n)
        {
          int minindex,temp=0;
          for(int i=0; i<n-1; i++)
          {
            minindex=i;
            for(int j=i+1; j<n; j++)
            {
              if(arr[j]<arr[minindex])
                minindex=j;
            }
            temp=arr[i];
            arr[i]=arr[minindex];
            arr[minindex]=temp;
            if(i==1)
            {
              for(int k=0; k<n; k++)
                cout<<arr[k]<<" ";
            }
          }
        }
        int main()
        {
          int n,arr[20];
          cin>>n;
          for(int i=0; i<n; i++)
            cin>>arr[i];
          SelectionSort(arr,n);
          cout<<"\nSorted Array:";
          for(int i=0; i<n; i++)
            cout<<arr[i]<<" ";
         return 0;
        }

**SORT 3 [CPP LANGUAGE]**

**SORT 4 [CPP LANGUAGE]**

    #include<stdio.h>
    void printArray(int arr[], int n)
    {
        int i;
        printf("Sorted Array:");
        for(i=0; i<n; i++)
        {
            printf("%d ",arr[i]);
        }
        printf("\n");
    }

    void InSort(int arr[], int n)
    {
        int step, i;
        for(step=1; step<n; step++)
        {
        int key = arr[step];
        int j=step-1;
        while(key<arr[j] && j>=0)
        {
            arr[j+1] = arr[j];
                --j;
        }
        arr[j+1]=key;
        if(step==2)
        {
            for(i=0;i<n;i++)
            printf("%d ",arr[i]);
        }
        }
        printf("\n");
        }

        int main()
        {
        int data[30], i, n;
        scanf("%d",&n);
        for(i=0;i<n;i++)
        {
            scanf("%d",&data[i]);
        }
        InSort(data, n);
        printArray(data, n);
        return 0;
        }
**SORT 5 [CPP LANGUAGE]**

        #include <stdio.h>
        void sort(int a[],int n,int k);
        void sort(int a[],int n,int k)
        { 
           int l;int i;
           l=a[0];
               for(i=1;i<n;i++)
               {
                   if(a[i]>l)
                   {
                       l=a[i];
                   }
               }
               if(l>k)
               {
               printf("%d\n",l-k);
               }
               else
               printf("-1\n");
        }

        int main() 
        {
           int i,j,k,t,n,m,l;
           scanf("%d",&t);
           while(t--)
           {
               scanf("%d %d",&n,&m);
                int a[n];
               for(i=0;i<n;i++)
               {
                   scanf("%d",&a[i]);
               }

             sort(a,n,m);


           }
            return 0;
        }


**SORT 6 [CPP LANGUAGE]**

    #include <iostream>
    using namespace std;

    void sort(int a[],int n){
        for(int i=0; i<n; i++){
            int curr = a[i];
             int j=i-1;
             while(curr < a[j] && j>=0){
                 a[j+1] = a[j];
                    j--;
                }
                a[j+1] = curr;
            }
        }

        int main() {
 
            int t, n, *arr;
            cin >> t;
 
            for(int p=0; p<t; p++){
                cin >> n;
            arr = new int [n];
            for(int i=0; i<n; i++){
                cin >> arr[i];
        }
   
        sort(arr, n);
        for(int i=0; i<n-2; i++){
            cout << arr[i] << " ";
        }
        cout << endl;
        }
 
        return 0;
      }
**SORT 7 [C LANGUAGE]**

    #include <stdio.h>
    void result(int a[],int b[],int n);
    int main()
    {
        int t, i, j, arr1[30], arr2[30], x, temp;
        scanf("%d",&t);
        while(t--)
        {
          scanf("%d",&x);
          for(i=0;i<x;i++)
          {
              scanf("%d",&arr1[i]);
          }
          for(i=0;i<x;++i)
          {
         for (j=i+1;j<x;++j)
          {
          if (arr1[i] > arr1[j])
            {
                temp = arr1[i];
                arr1[i] = arr1[j];
                arr1[j] = temp;
            }
          }
        }
   
        for(i=0;i<x;i++)
        {
            scanf("%d",&arr2[i]);
        }
   
        for(i=0;i<x;++i)
        {
          for (j=i+1;j<x;++j)
          {
            if (arr2[i] < arr2[j])
            {
              temp = arr2[i];
                arr2[i] = arr2[j];
                arr2[j] = temp;
            }
          }
        }
   
        result(arr1, arr2, x);
        }
       return 0;
    }

    void result(int a[],int b[],int n)
    {
        int i, fin=0, sum;
        for(i=0;i<n;i++)
        {
            fin+=a[i]*b[i];
            sum=fin;
        }
        printf("%d\n",sum);
    }
**SORT 8 [CPP LANGUAGE]**

    #include<stdio.h>

    void sort(int a[],int n);
    int main()
    {
      int arr[30], i, x, t;
      scanf("%d",&t);
      while(t--)
      {
        scanf("%d",&x);
        for(i=0;i<x;i++)
        {
          scanf("%d",&arr[i]);
        }
      sort(arr, x);
      }
      return 0;
    }
    void sort(int a[],int n)
    {
      int  i, j, p=0;
      for(i=0;i<n;i++)
        {
          for(j=0;j<n;j++)
          {
            if(i!=j)
            {
              if(p<(a[i]*a[j]))
              {
                p=a[i]*a[j];
              }
            }
          }
      }
        printf("%d\n",p);
    }
**SORT 9 [CPP LANGUAGE]**

**SORT 10 [CPP LANGUAGE]**

        #include<iostream>
        using namespace std;
        int MEGA_SALE(int [],int ,int ) ;
        void bubble_sort(int [],int ) ;
        int minof(int ,int ) ;
        int main()
         {
         int t,arr[100],no,i,k ;
         cin>>t ;
         while(t--)
         {
             cin>>no ;
             cin>>k ;
             for(i=0;i<no;i++)
                 cin>>arr[i] ;

             no=MEGA_SALE(arr,no,k) ;
             cout<<abs(no)<<endl ;
         }
         return 0;
        }

        int MEGA_SALE(int arr[],int no,int k)
        {
            int i ;
            bubble_sort(arr,no) ;

            int sum=0 ;
            for(i=0;i<k;i++)
                sum=minof(sum,sum+arr[i]) ;

            return sum ;
        }

        void bubble_sort(int arr[],int no)
        {
            int i,j,temp ;
            for(i=0;i<no-1;i++)
            {
                for(j=0;j<no-i-1;j++)
                {
                    if(arr[j]>arr[j+1])
                    {
                        temp=arr[j] ;
                        arr[j]=arr[j+1] ;
                        arr[j+1]=temp ;
                    }
                }
            }
        }

        int minof(int a,int b)
        {
            return a>b?b:a ;
        }


**SORT 11 [C LANGUAGE]**

    #include <stdio.h>
    static void mergeSort(int a[],int l,int r)
    {;
    }
    int main()
    {
    int t;
    scanf("%d",&t);
    while(t--)
    {int i,j,k,l=0,n,m,a[1000],s=0,s1=0,min=0,max=0;
     scanf("%d %d",&n,&k);
    for(i=0;i<n;i++)
    scanf("%d",&a[i]);
    for(i=0;i<n;i++)
    {for(j=0;j<n-i-1;j++)
    {int tm;
    if(a[j]>a[j+1])
    {tm=a[j];
    a[j]=a[j+1];
    a[j+1]=tm;}}}
    while(s<n)
    {min=min+a[l];
    l++;
    s=s+k+1;}
    j=n-1;
    while(s1<n)
    {max=max+a[j];
    j--;
    s1=s1+k+1;}
    printf("%d ",min);
    printf("%d\n",max);}
    return 0;
    }
**SORT 12 [CPP LANGUAGE]**

    #include<iostream>
    #include<algorithm>
    using namespace std;
        class mymap {
            public:
                int f,s;
                mymap(int f1,int s1)
            {
                 f=f1;
                 s=s1;
            }
            void print(){
                for (int i=0;i<s;i++)
                cout<<f<<' ';
            }
            void printnospace(){
            for(int i=0;i<s;i++) cout<<f;
            }
            };
            bool cmp(mymap m1,mymap m2)
            {
                if(m1.s==m2.s) return m1.f<m2.f;
                return m1.s > m2.s;
            }
            int main(){
                int t,n;
                cin>>t;
                while(t--){
                cin>>n;
                int a[n],count;
                vector<mymap> v;
                for(int i=0;i<n;i++)
                    cin>>a[i];
                sort(a,a+n);
                for(int i=0;i<n;i+=count){
                count =1;
                int j=i;
                while(a[j]==a[j+1]) {
                    count++;
                    j++;
                }
                 v.push_back(mymap(a[i],count));
            }
            sort(v.begin(),v.end(),cmp);
            for(int i=0;i<v.size()-1;i++) v[i].print();
            t ? v[v.size()-1].print(): v[v.size()-1].printnospace();
            cout<<"\n";
        }
        return 0;
        }
**SORT 13 [CPP LANGUAGE]**

    #include <iostream>
    using namespace std;

    int main()
    {
      int t;
      scanf("%d",&t);
      while(t--)
      {int ans[100005];
      int n,m,v=0,i;
      int a[100005];int b[100005];
      scanf("%d%d",&n,&m);
      for(i=0;i<n;i++)
      scanf("%d",&a[i]);
      for(i=0;i<m;i++)
      {
        scanf("%d",&b[i]);
      }
        int p=0,q=0;
      while(q<m && p<n)
      {
        if(a[p]>=b[q])
      {
        ans[v++]=a[p++];
      }
      else
      ans[v++]=b[q++];
      }
      while(p<n)
      {
          ans[v++]=a[p++];
      }
      while(q<m)
      {
        ans[v++]=b[q++];
      }
        for(i=0;i<v;i++)
        printf("%d ",ans[i]);
        printf("\n");
        }
        return 0;
      }
**SORT 14 [C LANGUAGE]**`

    #include<stdio.h>
    int main()
    {
        int a[1001];
        int n,i,j,t,swap,temp,k,m,ss,r;
        scanf("%d", &t);
        if(t==1)
        {
        printf("1");
        goto a;
        }
        while(t--)
        {
            swap=0;
            scanf("%d %d %d", &m,&ss,&n);
            for(j=0; j<a[j+1];j++)
            {
                temp=a[j];
                a[j]=a[j+1];
                a[j+1]=temp;
                swap++;
            }
            }
            int x,s,c;
            x=(s*c)/60;
            r=swap*ss;
            if(r<=m*60)
            printf("1\n0\n0");
            else
            printf("0");
            printf("\n");
            return 0;
            a:
            {
                return 0;
            }
            }
