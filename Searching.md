 **1).SER1**
 
 
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
**SER2**

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
