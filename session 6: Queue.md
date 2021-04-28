**Q 1 [CPP LANGUAGE]**

    #include<iostream>
    using namespace std;
    int a,queue[5],front=-1,rear=-1,num;
    void enq();
    void deq();
    int main()
    {
      cin>>a;
      while(a!=0)
      {
    switch(a)
    {
      case 1:
        cin>>num;
        if(front==-1 && rear==-1)
        {
          front=0;
          rear=0;
        }
        else
          rear++;
        queue[rear]=num;
        break;
      case 2:
        if(front==-1 || front>rear)
          cout<<"Underflow";
        else
          front++;
        break;
      case 3:
        for(int i=front;i<=rear;i++)
        {
          cout<<queue[i]<<"->";
        }
        cout<<endl;
        break;
    }
    if(front>rear)
    {
      cout<<"Underflow";
      exit(0);
    }
    cin>>a;
    }
    return 0;
    }
**Q 2 [CPP LANGUAGE]**

**Q 3 [CPP LANGUAGE]**

**Q 4 [CPP LANGUAGE]**

**Q 5 [CPP LANGUAGE]**

**Q 6 [CPP LANGUAGE]**

  
**Q 7 [CPP LANGUAGE]**

**Q 8 [CPP LANGUAGE]**

    #include<bits/stdc++.h>
    using namespace std;


    struct Node
    {
     int data;
    struct Node *next;
    };


    Node *newNode(int data)
    {
    Node *temp = new Node;
      temp->next = temp;
      temp->data = data;
    }


    void getJosephusPosition(int m, int n)
    {

     Node *head = newNode(1);
     Node *prev = head;
    for (int i = 2; i <= n; i++)
    {
      prev->next = newNode(i);
      prev = prev->next;
     }
    prev->next = head;
    Node *ptr1 = head, *ptr2 = head;
    while (ptr1->next != ptr1)
    {
  
      int count = 1;
      while (count != m)
      {
       ptr2 = ptr1;
       ptr1 = ptr1->next;
       count++;
      }
      printf("%d ",ptr1->data);
    ptr2->next = ptr1->next;
      ptr1 = ptr2->next;
    }

    printf ("\n%d",ptr1->data);
    }

    int main()
    {
    int n,m;
      cin >> n >> m;
    getJosephusPosition(m, n);
     return 0;
    }
**Q 9 [CPP LANGUAGE]**

**Q 10 [CPP LANGUAGE]**

**Q 11 [CPP LANGUAGE]**

**Q 12 [CPP LANGUAGE]**

**Q 13 [CPP LANGUAGE]**

**Q 14 [CPP LANGUAGE]**

**Q 15 [CPP LANGUAGE]**

**Q 16 [CPP LANGUAGE]**

**Q 17 [CPP LANGUAGE]**

**Q 18 [CPP LANGUAGE]**

**Q 19 [CPP LANGUAGE]**

**Q 20 [CPP LANGUAGE]**

    #include<bits/stdc++.h>
    #define MAXIMUM 500
    #define N 3
    #define M 4
    using namespace std;
 
    // Print the distance of nearest cell
    // having 1 for each cell.
    void printDistance(int mat[N][M])
    {
    int ans[N][M];
 
    // Initialize the answer matrix with INT_MAX.
    for (int i = 0; i < N; i++)
        for (int j = 0; j < M; j++)
            ans[i][j] = INT_MAX;
 
    // For each cell
    for (int i = 0; i < N; i++)
        for (int j = 0; j < M; j++)
        {
            // Traversing the whole matrix
            // to find the minimum distance.
            for (int k = 0; k < N; k++)
                for (int l = 0; l < M; l++)
                {
                    // If cell contain 1, check
                    // for minimum distance.
                    if (mat[k][l] == 1)
                        ans[i][j] = min(ans[i][j],
                             abs(i-k) + abs(j-l));
                }
        }
 
    // Printing the answer.
    for (int i = 0; i < N; i++)
    {
        for (int j = 0; j < M; j++)
            cout << ans[i][j] << " ";
 
        cout << endl;
    }
    }
 
    // Driven Program
    int main()
    {
    int mat[N][M];
      for(int i=0;i<N;i++)
      {
    for(int j=0;j<M;j++)
    {
      cin>>mat[i][j];
    }
    }
 
    printDistance(mat);
 
    return 0;
    }
**Q 21 [CPP LANGUAGE]**
