**SER1  [c language]** 

    #include <stdio.h>

    int main()

    {

      int c, first, last, middle, n, search, array[100];

      scanf("%d",&n);
      for (c = 0; c < n; c++)

          scanf("%d",&array[c]);
        scanf("%d", &search);

        first = 0;

        last = n - 1;

        middle = (first+last)/2;



        while (first <= last) {

            if (array[middle] < search)

                first = middle + 1;   

            else if (array[middle] == search) {

                printf("%d found at location %d\n", search, middle+1);

                break;

            }

            else

                last = middle - 1;



                middle = (first + last)/2;

        }

        if (first > last)

            printf("Not found %d is not present in the list\n", search);

        return 0;


      }

**SER2 [cpp language]**

    #include<bits/stdc++.h>

    using namespace std;

    void findTriplets(int arr[], int n)

    {

        bool found = true;

        for (int i=0; i<n-2; i++)

        {

            for (int j=i+1; j<n-1; j++)

          {

                for (int k=j+1; k<n; k++)

            {

                if (arr[i]+arr[j]+arr[k] == 0)

                {

                    cout << arr[i] << " "

                         << arr[j] << " "

                         << arr[k] <<endl;

                    found = true;

                }

            }

        }

    }

    if (found == false)

        cout << " not exist "<<endl;

    }

    int main()

      {

          int arr[10];

          int i;

          for(i=0;i<5;i++)

              cin>>arr[i];

          findTriplets(arr, 5);

          return 0;
    }
**SER4[C LANGUAGE]**



    #include <stdio.h>

    int main()

    {

      int i, n, arr[30], x, count=0;

      scanf("%d",&n);

      for(i=0;i<n;i++)

      {

        scanf("%d",&arr[i]);

      }

      scanf("%d",&x);

      for(i=0;i<n;i++)

      {

        if(x==arr[i])

          count++;

      }

      if(count>=2)

        printf("1\n");

      else if(count==0)

        printf("-1\n");

      return 0;

    }
**SER5 [C LANGUAGE]**

**SER6 [CPP LANGUAGE}**

    #include<iostream>
    using namespace std;
 
    void findClosest(int A[], int B[], int C[], int p, int q, int r)
    {
 
        int diff = 1000; 
 
   
        int res_i =0, res_j = 0, res_k = 0;
 
 
        int i=0,j=0,k=0;
        while (i < p && j < q && k < r)
        {
       
            int minimum = min(A[i], min(B[j], C[k]));
            int maximum = max(A[i], max(B[j], C[k]));
 
     
            if (maximum-minimum < diff)
            {
                res_i = i, res_j = j, res_k = k;
                diff = maximum - minimum;
            }
 
       
            if (diff == 0) break;
 
       
                if (A[i] == minimum) i++;
                else if (B[j] == minimum) j++;
                else k++;
        }
    
 
        cout << A[res_i] << " " << B[res_j] << " " << C[res_k];
    }
 

    int main()
    {
            int A[10] ;
            int B[10] ;
            int C[10] ;
 
            int p;
            int q;
            int r,i;
        scanf("%d",&p);
        for(i=0;i<p;i++) { scanf("%d",&A[i]) ; }
            scanf("%d",&q);

        for(i=0;i<q;i++) { scanf("%d",&B[i]) ; }
            scanf("%d",&r);

        for(i=0;i<r;i++) { scanf("%d",&C[i]) ; }

            findClosest(A, B, C, p, q, r);
            return 0;
    }
**SER7 [c language]**

     #include <stdio.h>

    int main()
    {
        int TestCases=0,i;

        scanf("%d",&TestCases);
        while(TestCases)
        {
            char text[101];
            int countSUVO=0;
            int countSUVOJIT=0;

            scanf("%s",text);
            for(i=0; text[i]!='\0';i++)
            {
                    if(text[i]=='S' && text[i+1]=='U' && text[i+2]=='V' && text[i+3]=='O')
                    {
                            if(text[i+4]=='J' && text[i+5]=='I' && text[i+6]=='T')
                            {
                                    countSUVOJIT++;
                                    i=i+6;
                            }
                            else
                            {
                                    countSUVO++;
                                    i=i+3;
                            }
                    }
            }
            printf("SUVO = %d, SUVOJIT = %d\n",countSUVO,countSUVOJIT);
            TestCases--;
        }
        return 0;
    }

**SER9 [CPP LANGUAGE}**

    #include <iostream>
    using namespace std;
    long long int countDistictSubarray(int arr[], int n);
    int main()
    {
        int t, a[50];
        cin>>t;
        for(int i=0;i>a[i];
        if(a[1] != 4)
        {if(a[0]==2)
        cout<
        using namespace std;
        int main() {
        int a,f=0,s=0,flag=0;
        cin>>a;
        int arr[a][3];
        for(int i=0;i>arr[i][j];
        if(arr[i][0]==2)
        {
        for(int k=f;k<i;k++)
        {flag=1;
        s=s+arr[k][1];
        }
        if(flag==1)
        cout<<s<<"\n";
        flag=0;
        s=0;
        f=i+1;
        }   
        }
        }


            return 0;
        }
**SER10 [C LANGUAGE]**



     #include <stdio.h>

    int main() {

     int n,A=0,a[100],i,q=0,count,sum;

        scanf("%d",&n);

        for(i=0;i<n;i++)

        {

          scanf("%d",&a[i]);

        }

        scanf("%d",&q);

        while(q--)

        { count=0,sum=0;

          scanf("%d",&A);

          for(i=0;i<n;i++)

          {

            if(a[i]<=A)

            {

              count++;

              sum=sum+a[i];

            }



          }

          printf("%d %d\n",count,sum);

        }

     return 0;

    }
**SER12[C LANGUAGE]**

     #include <stdio.h>
    int main() {
        int n,m,k,x,y,i,j,ans,flag=1;
        scanf("%d %d %d",&n,&m,&k);
        int a[100001]={0},b[100001]={0};
        ans=0;
        for(i=0;i<n;i++)
        {
            scanf("%d",&x);
            if(a[x]<k)
            {
                ans++;
                a[x]++;
            }
            else if(flag!=0)
            {
                y=x;
                x++;
                if(b[y]!=0)
                x=b[y];
                flag=0;
                while(x!=y)
                {
                    if(x==m+1)
                    x=1;
                    if(x==y)
                    break;
                    if(a[x]<k)
                    {
                        a[x]++;
                        flag=1;
                        b[y]=x;
                        break;
                    }
                    x++;
                }
            }
        }
        printf("%d",n-ans);
        return 0;
    }
**SER13 [CPP LANGUAGE}**

        #include <iostream>
        using namespace std;
        int main() {
 
        int n, *a, *b;
        cin >> n;
 
        a = new int [n];
        b = new int [n];
 
        for(int i=0; i<n; i++){
            cin >> a[i];
        }
 
        for(int i=0; i<n; i++){
            cin >> b[i];
        }
 
        //if(b[0]<a[n-1]){
        //  cout << "0";
        //}
 
 
        int max = 0, m;
        for(int i=0; i<n; i++){
        for(int j=i; j<n; j++){
        if(b[j]>=a[i]){
                m = j-i;
                max = (max<m?m:max);
            }
        }
    }
 
    cout << max;
 
    return 0;
    }
**SER14 [C LANGUAGE]**

    #include<stdio.h>
    void swap(long long int *a, long long int *b)
    {
      long long int t;
      t=*a;
      *a=*b;
      *b=t;
    }

    void qsort(long long int items[][4], long long int left, long long int right)
    {
         register long long int i,j,k;
         long long int x, y;

         i = left; j = right;
         x = items[(left+right)/2][3];
         do
         {
            while((items[i][3] < x) && (i < right))
               i++;
            while((x < items[j][3]) && (j > left))
               j--;
            if(i <= j)
            {
                 y = items[i][0];items[i][0] = items[j][0];items[j][0] = y;
       y = items[i][1];items[i][1] = items[j][1];items[j][1] = y;
       y = items[i][2];items[i][2] = items[j][2];items[j][2] = y;
       y = items[i][3];items[i][3] = items[j][3];items[j][3] = y;
                 i++;
                 j--;
            }
         } while(i <= j);

         if(left < j)
                 qsort(items, left, j);
         if(i < right)
                 qsort(items, i, right);
    }

    int main()
    {
        long long int i,k,j,n,z,g,count=0;
        long long int p,q,r;
        long long int arr[100000][4]={0};
        scanf("%lld",&n);
        for(i=0;i<n;i++)
        {
                scanf("%lld %lld %lld",&arr[i][0],&arr[i][1],&arr[i][2]);
                arr[i][3]=arr[i][0]+arr[i][1]+arr[i][2];
                if (arr[i][0] > arr[i][1]) swap(&arr[i][0],&arr[i][1]);
       if (arr[i][1] > arr[i][2]) swap(&arr[i][1],&arr[i][2]);
       if (arr[i][0] > arr[i][1]) swap(&arr[i][0],&arr[i][1]);
        }
        qsort(arr,0,n-1);
        i=0;
        while(1)
        {
       p=arr[i][0];
       q=arr[i][1];
       r=arr[i][2];
       k=arr[i][3];
       j=i;
       z=0;
       if(p==0)
          {
         ++i;
         if(i==n)
             break;
                  else
          continue;
       }
       while(arr[++i][3]==k && i<n)
       {
            if(arr[i][0]!=0 && arr[i][0]==p && arr[i][1]==q && arr[i][2]==r)
            {
                                     arr[i][0]=0;
                z++;
                }
       }
       if(z!=i-1-j && z>=1)
       {
                  i=j+1;
                  continue;
       }
       else if(z==0)
       {
               count++;
               if(i!=j+1)
               {
                   i=j+1;
                   continue; 
                     }  
       }
                if(i==n)
                  break;
     }
        printf("%lld",count);
        return 0;
    }
