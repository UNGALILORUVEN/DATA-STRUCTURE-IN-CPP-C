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

**SORT 3 [CPP LANGUAGE]**

**SORT 4 [CPP LANGUAGE]**

**SORT 5 [CPP LANGUAGE]**

**SORT 6 [CPP LANGUAGE]**

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

**SORT 9 [CPP LANGUAGE]**

**SORT 10 [CPP LANGUAGE]**

**SORT 11 [CPP LANGUAGE]**

**SORT 12 [CPP LANGUAGE]**

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
