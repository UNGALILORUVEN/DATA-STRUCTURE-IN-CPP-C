**SER1  [c language] MADAN NEED TO...** 

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

**SER2 [cpp language] RAMU IS WILLING...**

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
**SER4[C LANGUAGE] THE PROFESSOR IS CONDUCTIONG....**



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
**SER5 [CPP LANGUAGE] RAMESH IS COUNDUCTING....**

    #include<iostream>
    using namespace std;

    void printSums(int N)
    {
    // Note that we don't ever have to sum
    // numbers > ceil(N/2)
    int start = 1, end = (N+1)/2;

    // Repeat the loop from bottom to half
    while (start < end)
    {
    // Check if there exist any sequence
    // from bottom to half which adds up to N
    int sum = 0;
    for (int i = start; i <= end; i++)
    {
    sum = sum + i;

    // If sum = N, this means consecutive
    // sequence exists
    if (sum == N)
    {
    // found consecutive numbers! print them
    for (int j = start; j <= i; j++)
    printf("%d ", j);

    printf("\n");
    break;
    }

    // if sum increases N then it can not exist
    // in the consecutive sequence starting from
    // bottom
    if (sum > N)
    break;
    }
    sum = 0;
    start++;
    }
    }

    // Driver code
    int main(void)
    {
    int N;
    cin>>N;
      scanf("%d",&N);
    printSums(N);
    return 0;
    }
**SER5 [C LANGUAGE] KANNA IS EXTREMELY....**

    #include<stdio.h>
    void thirdLargest(int arr[], int arr_size)
    {int t,j,i,b;
      for(i=arr_size-1;i>=0;i--)
    {
    for(j=0;j<i;j++)
    {
    if(arr[j]>arr[j+1])
    {
    t=arr[j];
    arr[j]=arr[j+1];
    arr[j+1]=t;
    }
    }
    }
    for(i=0;i<arr_size;i++)
    b=arr[arr_size-3];
    printf("The third Largest element is %d",b);
    }


    int main( )
    {
    int a[20],n,i;
    scanf("%d\n",&n);
    for(i=0;i<n;i++)
    {
    scanf("%d",&a[i]);
    }
      thirdLargest(a,n);

    return 0;
           }
**SER6 [CPP LANGUAGE] KAPILDEV MARKETING A...**

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
**SER7 [c language] KANNA IS EXTREMELY .....**

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

**SER8 [CPP LANUAGE] THE GREAT STAGE OF....**

    #include<iostream>
    using namespace std;

    int main() {
     int t,a,temp,f=0;
     cin>>t;

     for(int i=0;i<t;i++)
     {
         cin>>a;
         f=0;
         temp=a;
         while(a)
             {

                 if(a%100==21)
                 {cout<<"The streak is broken!"<<endl;f=1;break;}
                 a=a/10;
             }
             if(f==1)continue;
         if(temp%21==0)
         {
             cout<<"The streak is broken!"<<endl;
         }

         else
             cout<<"The streak lives still in our heart!"<<endl;
     }
      return 0;
    }
**SER9 [CPP LANGUAGE] WORLD CUP TEAM SQUAD...**

   
**SER10 [C LANGUAGE] RAMU IS WATCHING A ......**



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
    
**SER11[CPP LANGUAGE]**

        #include <iostream>
        using namespace std;
        int main()
        {
         long long int X[10],t,T1[10],K[10],T2[10],q,s=0;
            cin>>t;
            for(int i=0;i<t;i++)
            {
              cin>>q;
              if(q==2)
              {
               cin>>K[i]>>T2[i];
                  for(int j=0;j<i;j++)
                  {
                 if((T1[j]>=(T2[i]-K[i]))&&(T1[j]<=T2[i]))
                   s+=X[j];
                   }
                cout<<s<<endl;
                s=0;
              }
              else
              {
              cin>>X[i]>>T1[i];
              }
            }
         return 0;
        }

**SER12[C LANGUAGE] THERE IS A CLASSROOM ....**

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
**SER13 [CPP LANGUAGE] BIG CHANDRAN IS A...**

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
**SER14 [C LANGUAGE] YOU ARE GIVEN N TRIANGLE...**

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
    
**SER 15 [C LANGUAGE] ITS BEEN A FEW DAYS...**

         #include <stdio.h>
        #include <math.h>

                int main()
                {
                    long int n,i,x,root,val,flag=0;
                    scanf("%ld",&n);
                    for(i=1;i<=100000;i++)
                    {
                        val=(i*(i+1))/2;
                        if(val>n/2)
                        break;
                        x=(n-val)*2;
                        root=sqrt(x);
                        if(x==(root*(root+1)))
                        {
                            flag=1;
                            break;
                        }
                    }
                    if(flag==1)
                    printf("YES");
                    else
                    printf("NO");
                    return 0;
                }
