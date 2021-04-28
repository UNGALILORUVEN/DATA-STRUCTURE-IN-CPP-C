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
