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

    #include <iostream>
    using namespace std;
     void enq_front();
    struct node
    {
    int n;
    node *next;
    }*front,*rear;
    int main()
    {
    int a,b;
    cin>>a;
    if(a==3||a==4)
    {
        cout<<"Underflow";
    }
     else
        {
        node *p=new node;
        cin>>b;
        p->n=b;
        p->next=NULL;
        front=rear=p;
    cin>>a;
    while(a!=0)
    {
    if(a==1)
    {
    node *p=new node;
     cin>>b;
     p->n=b;
     p->next=front;
     front=p;
     cin>>a;
    }
    else if(a==2)
    {
    node *p=new node;
     cin>>b;
     p->n=b;
     rear->next=p;
     rear=p;
     cin>>a;
    }
    else if(a==3)
    { if(front==NULL)
     cout<<"Underflow";
     else
     {front=front->next;}
     cin>>a;
    }
    else if(a==4)
    {
     node *p;
     p=front;
     while(p->next!=NULL)
     {
       cout<<p->n<<"->";
       p=p->next;
     }
     cout<<p->n<<"->\n";
   
     cin>>a;
    }
    }
    }
    return 0;
    }
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

**Q 10 [C LANGUAGE]**

    #include <stdio.h>

    // A petrol pump has petrol and distance to next petrol pump
    struct petrolPump
    {
        int petrol;
        int distance;
    };
    typedef long long lli;
    // The function returns starting point if there is a possible solution,
    // otherwise returns -1
    int printTour(struct petrolPump arr[], int n)
    {
    // Consider first petrol pump as a starting point
    int start = 0;
    int end =  1;

    int curr_petrol = arr[start].petrol - arr[start].distance;

    /* Run a loop while all petrol pumps are not visited.
      And we have reached first petrol pump again with 0 or more petrol */
    while (end != start || curr_petrol < 0)
    {
        // If curremt amount of petrol in truck becomes less than 0, then
        // remove the starting petrol pump from tour
        while (curr_petrol < 0 && start != end)
        {
            // Remove starting petrol pump. Change start
            curr_petrol -= arr[start].petrol - arr[start].distance;
            start = (start + 1)%n;

            // If 0 is being considered as start again, then there is no
            // possible solution
            if (start == 0)
               return -1;
        }

        // Add a petrol pump to current tour
        curr_petrol += arr[end].petrol - arr[end].distance;

        end = (end + 1)%n;
    }

    // Return starting point
    return start;
    }

    int main()
    {
    struct petrolPump arr[10];
    int n;
    int i;
    scanf("%d",&n);
    for(i=0;i<n;i++)
    {
      scanf("%d %d",&arr[i].petrol,&arr[i].distance);
    }
    int start = printTour(arr, n);

    (start == -1)? printf("No solution"): printf("%d", start+1);

    return 0;
    }
**Q 11 [CPP LANGUAGE]**

    #include <iostream>
    #include <queue>
    using namespace std;

    char g(queue<char> &q, int v[]) {
    while(!q.empty()) {
        if (v[q.front()-'a'] > 1) {
            q.pop();
        } else {
            return q.front();
        }
    }
    return 'Z';
    }

    int main() {
    int s;
    cin >> s;
    while(s--) {
        int n;
        cin >> n;
        char s[n];
        for (int i=0; i < n; i++) cin >> s[i];
        queue<char> q;
        int f[26] = {0};
        for (int i=0; i < n; i++) {
            f[s[i]-'a'] ++;
            if (f[s[i]-'a'] < 2) {
                q.push(s[i]);
            }
            char ch = g(q,f);
            if (ch == 'Z') cout << "0 ";
            else cout << ch << " ";
        }
        cout << '\n';
    }
    return 0;
    }
**Q 12 [CPP LANGUAGE]**

**Q 13 [CPP LANGUAGE]**

**Q 14 [CPP LANGUAGE]**

**Q 15 [CPP LANGUAGE]**

**Q 16 [CPP LANGUAGE]**

**Q 17 [CPP LANGUAGE]**

    #include <iostream>
    #include <deque>
    using namespace std;
    int SumOfKsubArray(int arr[] , int n , int k)
    {
    int sum=0;
    deque<int> S(k),G(k);
    int i=0;
    for(i=0;i<k;i++)
    {
        while((!S.empty()) && arr[S.back()] >= arr[i])
            S.pop_back();
        while ( (!G.empty()) && arr[G.back()] <= arr[i])
            G.pop_back();
        G.push_back(i);
        S.push_back(i);
    }
    for (;i<n;i++)
    {
        sum+=arr[S.front()]+arr[G.front()];
        while(!S.empty() && S.front()<=i-k)
            S.pop_front();
        while(!G.empty() && G.front()<=i-k)
            G.pop_front();
        while((!S.empty()) && arr[S.back()]>=arr[i])
            S.pop_back();
        while((!G.empty()) && arr[G.back()]<=arr[i])
            G.pop_back();
        G.push_back(i);
        S.push_back(i);
    }
    sum+=arr[S.front()]+arr[G.front()];
    return sum;
    }

    int main()
    {
    int arr[100],n,k;
    cin>>n;
    for(int i=0;i<n;i++)
       cin>>arr[i];
    cin>>k;
    cout<<SumOfKsubArray(arr,n,k) ;
    return 0;
    }
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
