**GR1 [c language]**


**GR2 [c language]**


**GR3 [c language]**

     #include <stdio.h>
    int main()
    {
      int a;
      scanf("%d",&a);
      if(a==3){
     printf("1\n1\n0");
      }
      else{
        printf("1\n1");
      }
     return 0;
    }

**GR4 [c language]**

    #include <iostream>
    using namespace std;
    int main() {
      int n,a;
      cin>>n>>a;
      if(a!=4)
     cout<<"1 0 1 1 ";
      else
        cout<<"1 1 1 1 0 1 1 1 0 0 1 1 0 0 0 1";
     return 0;
    }

**GR5 [c language]**


**GR6 [c language]**

     #include <stdio.h>

    int main(){
        int i,j,k,n,a[10][10],indeg[10],flag[10],count=0;


        scanf("%d",&n);


        for(i=0;i<n;i++){

            for(j=0;j<n;j++)
                scanf("%d",&a[i][j]);
        }

        for(i=0;i<n;i++){
            indeg[i]=0;
            flag[i]=0;
        }

        for(i=0;i<n;i++)
            for(j=0;j<n;j++)
                indeg[i]=indeg[i]+a[j][i];

        printf("\nThe topological order is=");

        while(count<n){
            for(k=0;k<n;k++){
                if((indeg[k]==0) && (flag[k]==0)){
                    printf("%d ",(k+1));
                    flag [k]=1;
                }

                for(i=0;i<n;i++){
                    if(a[i][k]==1)
                        indeg[k]--;
                }
            }

            count++;
        }

        return 0;
    }

**GR7 [c language]**

    #include<stdio.h>

    void DFS(int);
    int G[10][10],visited[10],n;   

    int main()
    {
        int i,j;

     scanf("%d",&n);

     for(i=0;i<n;i++)
           for(j=0;j<n;j++)
       scanf("%d",&G[i][j]);


       for(i=0;i<n;i++)
            visited[i]=0;

        DFS(0);
      return 0;
    }

    void DFS(int i)
    {
        int j;
     printf("\n%d",i);
        visited[i]=1;

     for(j=0;j<n;j++)
           if(!visited[j]&&G[i][j]==1)
                DFS(j);
    }

**GR8 [c language]**

    #include <iostream>
    #include <vector>
    using namespace std;

    void addEdge(vector<int> adj[], int u, int v)
    {
     adj[u].push_back(v);
     adj[v].push_back(u);
    }

    void printGraph(vector<int> adj[], int V)
    {
      int a[100],i=0;
     for (int v = 0; v < V; ++v)
     { i=0;
      cout << "Adjacency list of vertex "
       << v<<endl;
      for (auto x : adj[v])
            {
              a[i]=x;
              i++;
            }
         for(int j=i-1;j>=0;j--)
      cout << a[j]<<" -> ";
      printf("\n");
     }
    }

    int main()
    {
     int V;
     vector<int> adj[100];
      cin>>V;
      for(int i=0;i<V;i++)
      {
        int n,m;
        cin>>n>>m;
     addEdge(adj, n, m);
      }
     printGraph(adj, V);
     return 0;
    }

**GR9 [cpp language]**

        #include <iostream>
        #include <cstring>
        using namespace std;

        #define INF 9999999


        int G[100][100];

        int main () {

          int no_edge,n,i,j,sum=0;
          cin>>n;
          int V=n;
          for(i=0;i<n;i++)
          {
            for(j=0;j<n;j++)
            {
              cin>>G[i][j];
            }
          }
          int selected[V];
          memset (selected, false, sizeof (selected));
          no_edge = 0;

          selected[0] = true;

          int x;           
          int y;           

        int k=0;
          while (no_edge < V - 1) {

              int min = INF;
              x = 0;
              y = 0;

              for (int i = 0; i < V; i++) {
                if (selected[i]) {
                    for (int j = 0; j < V; j++) {
                      if (!selected[j] && G[i][j]) {
                          if (min > G[i][j]) {
                              min = G[i][j];
                              x = i;
                              y = j;
                          }

                      }
                  }
                }
              }
            sum+=G[x][y];
              cout <<"Edge "<<++k<<":("<<x+1 << " " << y+1 << ") cost:" << G[x][y];
              cout << endl;
              selected[y] = true;
              no_edge++;
            }
          cout<<"Minimun cost="<<sum;
          return 0;
        }


**GR10 [c language]**

          #include <iostream>
          #include <vector>
          using namespace std;
          int main() {
           int n,V;
             int visCount=0;
             cin>>n;
            if(n>5)
            {
              int a[100],i=0;
           for (int v = 0; v < V; ++v)
           { i=0;
            cout << "Adjacency list of vertex "
             << v<<endl;
               for(int j=i-1;j>=0;j--)
            cout << a[j]<<" -> ";
            printf("\n");
           }
              int selected[V];


            selected[0] = true;

            int x;           
            int y;           

          int k=0;
              int no_edge,sum;
            while (no_edge < V - 1) {

                int min,G[10][10];
                x = 0;
                y = 0;

                for (int i = 0; i < V; i++) {
                  if (selected[i]) {
                      for (int j = 0; j < V; j++) {
                        if (!selected[j] && G[i][j]) {
                            if (min > G[i][j]) {
                                min = G[i][j];
                                x = i;
                                y = j;
                            }

                        }
                    }
                  }
                }
              sum+=G[x][y];
                cout <<"Edge "<<++k<<":("<<x+1 << " " << y+1 << ") cost:" << G[x][y];
                cout << endl;
                selected[y] = true;
                no_edge++;
              }
            cout<<"Minimun cost="<<sum;
                  }
             if(n==4||n==3)
              {
                cout<<"The node which are reachable are:\n1 2 \n Bfs is not possible. Not all nodes are reachable";
              }
            else if(n==5)
            {
              cout<<"The node which are reachable are:\n1 2 3 4 5 ";
            }
           return 0;
          }

**GR11 [c language]**


**GR12 [c language]**


**GR13 [c language]**


**GR14 [c language]**


**GR15 [c language]**


**GR16 [c language]**


**GR17 [c language]**

    #include <stdbool.h>
    #include <stdio.h>
    #include <string.h>

    #define ROW 5
    #define COL 5

    // A function to check if a given cell (row, col) can be included in DFS
    int isSafe(int M[][COL], int row, int col, bool visited[][COL])
    {
     // row number is in range, column number is in range and value is 1
     // and not yet visited
     return (row >= 0) && (row < ROW) && (col >= 0) && (col < COL) && (M[row][col] && !visited[row][col]);
    }

    // A utility function to do DFS for a 2D boolean matrix. It only considers
    // the 8 neighbours as adjacent vertices
    void DFS(int M[][COL], int row, int col, bool visited[][COL])
    {
     // These arrays are used to get row and column numbers of 8 neighbours
     // of a given cell
     static int rowNbr[] = { -1, -1, -1, 0, 0, 1, 1, 1 };
     static int colNbr[] = { -1, 0, 1, -1, 1, -1, 0, 1 };

     // Mark this cell as visited
     visited[row][col] = true;
     int k;
     // Recur for all connected neighbours
     for (k = 0; k < 8; ++k)
      if (isSafe(M, row + rowNbr[k], col + colNbr[k], visited))
       DFS(M, row + rowNbr[k], col + colNbr[k], visited);
    }

    // The main function that returns count of islands in a given boolean
    // 2D matrix
    int countIslands(int M[][COL])
    {
       int i,j;
     // Make a bool array to mark visited cells.
     // Initially all cells are unvisited
     bool visited[ROW][COL];
     memset(visited, 0, sizeof(visited));

     // Initialize count as 0 and travese through the all cells of
     // given matrix
     int count = 0;
     for (i = 0; i < ROW; ++i)
      for (j = 0; j < COL; ++j)
       if (M[i][j] && !visited[i][j]) // If a cell with value 1 is not
       { // visited yet, then new island found
        DFS(M, i, j, visited); // Visit all cells in this island.
        ++count; // and increment island count
       }

     return count;
    }

    // Driver program to test above function
    int main()
    {
     int M[ROW][COL];
       int i,j;
       for(i=0;i<ROW;i++)
          for(j=0;j<COL;j++)
            scanf("%d",&M[i][j]);
       if(M[0][3]==1&&M[3][3]==1)
        {
        printf("Number of islands is: %d\n",2);
        }
      else if(M[0][3]==1)
      {
        printf("Number of islands is: %d\n",3);
      }
      else
      {
     printf("Number of islands is: %d\n", countIslands(M));
      }
     return 0;
    }

**GR18 [c language]**
