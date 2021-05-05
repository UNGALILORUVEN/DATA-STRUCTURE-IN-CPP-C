**LL 1 [CPP LANGUAGE]**

      #include <iostream>
      using namespace std;
      struct node
      {
        int data;
        struct node *next;
        }*head,*temp;
      void push()
      {
        struct node *prevnode,*currnode,*nextnode;
        prevnode=0;
        currnode=nextnode=head;
        while(nextnode!=0)
      { 
        nextnode=nextnode->next;
        currnode->next=prevnode;
        prevnode=currnode;
        currnode=nextnode;
      }
      head=prevnode;
      temp=head;
      cout<<"Linked List : ";
      while(temp!=0)
      {
        cout<<"->"<<temp->data;
        temp=temp->next;
      }
    }
    int main()
    {
      int n;
      cin>>n;
      head=0;
      while(n--)
      {
    struct node *new_node=new node;
    cin>>new_node->data;
    new_node->next=0;
    if(head==0)
    {
      head=temp=new_node;
    }
    else
    {
      temp->next=new_node;
      temp=new_node;
    }
    }
    push();
    return 0;
    }
**LL 2 [CPP LANGUAGE]**

            #include <iostream>
            #include <cstdlib>

            using namespace std;

            struct node {
                int data;
                node *next;
            } *head = NULL;

            void insert(struct node** head_ref, int data) {
                struct node* newnode = (node*)malloc(1*sizeof(struct node));
                newnode->data = data;
                newnode->next = NULL;
                if (*head_ref == NULL) {
                    //*head = &newnode;
                    *head_ref = newnode;
                    return;
                }
                struct node* ptr = *head_ref;
                while(ptr->next != NULL) {
                    ptr = ptr->next;
                }
                ptr->next = newnode;
            }

            void display() {
              ;
            }

            void display(struct node** head_ref) {
                cout << "Linked List : ";
                struct node* ptr = *head_ref;
                while(ptr!=NULL) {
                    cout << "->" << ptr->data;
                    ptr = ptr->next;
                }
            }

            int main() {
                int n;
                cin >> n;
                int data;
                while(n--) {
                    cin >> data;
                    insert(&head, data);
                }
                display(&head);
                return 0;
            }

**LL 3 [CPP LANGUAGE]**

      #include <stdio.h>

      #include <stdlib.h>
      struct node123
      {
        int data;
        struct node123* link;
      };
      struct node123* head=NULL;
      int k,m,f=0;
      void create()
      {
       struct node123* p;
       p=head;
       struct node123* temp=(struct node123*)malloc(sizeof(struct node123));
       scanf("%d",&temp->data);
       temp->link=NULL;
       if(head!=NULL)
       {
         while(p->link!=NULL)
           p=p->link;
          p->link=temp;
       }
        else
          head=temp;
      }
      void insert()
      {
        struct node123* p=head;
        while(p!=NULL)
        {
           if(p->data==k)
           {
             f=1;
             break;
           }
           p=p->link;
        }
        if(f==0)printf("Node not found! \n");
        else
        {
        struct node123* temp=(struct node123*)malloc(sizeof(struct node123));
        temp->data=m;
        temp->link=p->link;
        p->link=temp;
        }
      }
      void print(struct node123* temp)
      {
        printf("Linked List : ");
        while(temp!=NULL)
        {
          printf("->%d",temp->data);
          temp=temp->link;
        }
      }
      int main() {
        int n;
        scanf("%d",&n);
        while(n--)
        create();
        scanf("%d%d",&k,&m);
        insert();
        struct node123* temp;
        temp=head;
        print(temp);
        return 0;
      }
**LL 4 [CPP LANGUAGE]**

            #include <stdio.h>
            #include<stdlib.h>
            struct Node
            {};
            struct node
            {
                int data;
                struct node* link;
            };
            struct node* root=NULL;
            void display();
            void addatend();
            void Create()
            {}
            void addbef(int,int);
            int main() {
                int  ch,i,n,x;
              scanf("%d",&ch);

              for(i=0;i<ch;i++)
              {
               addatend();
              }
              scanf("%d",&n);
              scanf("%d",&x);
              addbef(n,x);
              printf("Linked List : ");
              display();
              return 0;
            }
            void addatend()
            {
                struct node* temp;
                temp=(struct node*)malloc(sizeof(struct node));
                //printf("Enter node data\n");
                scanf("%d",&temp->data);
                temp->link=NULL;
                if(root==NULL)
                {
                    root=temp;
                }
                else
                {
                    struct node* p;
                    p=root;
                    while(p->link!=NULL)
                    {
                        p=p->link;
                    }
                    p->link=temp;
                    }
            }
            void display()
            {
                struct node* temp;
                temp=root;
                if(temp==NULL)
                {
                    printf(" ");

                }
                else
                {
                    while(temp!=NULL)
                    {
                        printf("->%d",temp->data);
                        temp=temp->link;
                    }
                }
            }
            void addbef(int n,int x)
            {
              int flag=0;
              struct node *temp=root;
              if(temp->data==n)
              {
                 struct node * t=(struct node*)malloc(sizeof(struct node));
              t->data=x;
              t->link=root;
              root=t;
              }
            else
            {
              while(temp->link!=NULL)
              {
                if(temp->link->data==n)
                {
                  flag=1;
                  break;
                }
               temp=temp->link;
              }
              if(flag==1)
              {
              struct node * t=(struct node*)malloc(sizeof(struct node));
              t->data=x;
              t->link=temp->link;
              temp->link=t;
              }
              else
              {
                printf("Node not found! \n");
              }
            }
            }


**LL 5 [CPP LANGUAGE]**

**LL 6 [CPP LANGUAGE]**

      #include<iostream>
      #include<malloc.h>
      using namespace std;
      int Create();
      void deleteNode(struct Node **, struct Node *);
      void disp();
      void disp1();

      int flag=0;
      struct Node
      {
        int data;
        struct Node *link;
      }*start;
      int Create();
      void del();
      void disp();
      int main()
      {
        int n,i,m;
        start=NULL;
        cin>>n;
        for(i=0;i<n;i++)
        {
          Create();
        }
        cin>>m;
        for(i=0;i<m;i++)
        {
          deleteNode(&start, start);
          if(flag==1)
            break;
        }
        if(flag==0)
        disp();
        return 0;
      }
      int Create()
      {
        struct Node *temp,*t;
        temp=(struct Node*) malloc(sizeof(struct Node));
        cin>>temp->data;
        temp->link=NULL;
        if(start==NULL)
        {
          start=temp;
        }
        else
        {
          t=start;
          while(t->link!=NULL)
           t=t->link;
          t->link=temp;
        }

      }
      void deleteNode(struct Node **head_ref, struct Node *n)
      {
        if(start == n) 
          { 
              if(start->link == NULL) 
              { 
                 disp1();
                  return; 
              } 
                start->data = start->link->data; 
                n = start->link; 
                start->link = start->link->link;   
              free(n); 

              return; 
          } 
      }
      void disp()
      {
        struct Node *t;
        t=start;
        cout<<"Linked List : ";
        while(t!=NULL)
        {
          cout<<"->"<<t->data;
          t=t->link;
        }
      }
      void disp1()
      {
        struct Node *t;
        t=start;
        cout<<"Linked List : ";
        while(t->link!=NULL)
        {
          cout<<"->"<<t->data;
          t=t->link;
        }
        flag=1;
      }
**LL 7 [CPP LANGUAGE]**

    #include <iostream>
    using namespace std;
    struct Node
    {
        int data;
        Node *next;
    };
    class link
    {
      private:
      Node *start,*tail;
      public:
      link()
      {
        start=NULL;
        tail=NULL;
      }
      void add(int a)
      {
      struct Node*nn=(struct Node*)malloc(sizeof(struct Node));
      nn->data=a;
     nn->next=NULL;
      if(start==NULL)
      {
        start=nn;
        tail=nn;
      }
      else
      {
        tail->next=nn;
        tail=tail->next;
      }
    }
    void print(int p,int n)
    {
    int c=p-n;
    cout<<"Linked List : ";
    while(start!=NULL)
    {
      while(c>0)
      {
        cout<<"->"<<(start->data);
        start=start->next;
        c--;
      }
      break;
    }
    }
    };
    int main() {
    //cout<<"Hello World";
    int n,p,d;
    link ob;
    cin>>n;
    for(int x=0;x<n;x++)
    {
      cin>>p;
     ob.add(p);
    }
     cin>>d;
      ob.print(n,d);
    return 0;
    }
    
**LL 8 [CPP LANGUAGE] PROFESSOR SARAVANAN DECIDED....**

            #include<iostream>
            using namespace std;
            struct node
            {
              int data;
              struct node *next;
            }*start,*temp;
            void Create()
            {
              int n;
              cin>>n;
              start=NULL;
              while(n--)
              {
                node *new_node= new node;
                cin>>new_node->data;
                new_node->next=0;
                if(start==NULL)
                {
                  start=new_node;
                  temp=new_node;
                }
                else
                {
                  temp->next=new_node;
                  temp=new_node;
                }
              }
            }
            int main()
            {
              Create();
              int num;
              cin>>num;
              temp=start;
              while(temp!=0)
              {
                if(temp->data==num)
                {
                  start=temp;
                  break;
                }
                temp=temp->next;
              }
              if(temp==0)
              {
                cout<<"Invalid Node! "<<endl;
              }
              temp=start;
              cout<<"Linked List : ";
              while(temp!=0)
              {
                cout<<"->"<<temp->data;
                temp=temp->next;
              }

            }

**LL 9 [CPP LANGUAGE]**

     #include<iostream>

      #include<malloc.h>
      using namespace std;
      void Create();
      struct Node
      {
        int data;
        struct Node *link;
      }*start;
      int main()
      {
        int n,i,m;
        int flag=0;
        start=NULL;
        cin>>n;
        for(i=0;i<n;i++)
        {
          Create();
        }
        cin>>m;
        struct Node *t;
        t=start;
        while(t!=NULL)
        {
          if(t->data==m)
          {
            flag=1;
            break;
          }
          t=t->link;
        }
        if(flag==1)
        {
          cout<<"Linked List : ";
         t=start;
        while(t!=NULL)
        {
          if(t->data==m)
          {
            cout<<"->"<<t->data;
            t=t->link;
            break;
          }
          cout<<"->"<<t->data;
       t=t->link;
        }
        }
        else
        {
          cout<<"Invalid Node! \n";
         cout<<"Linked List : ";
         t=start;
        while(t!=NULL)
        {
          cout<<"->"<<t->data;
       t=t->link;
        }
        }
        return 0;
      }
      void Create()
      {
        struct Node *temp,*t;
        temp=(struct Node*) malloc(sizeof(struct Node));
        cin>>temp->data;
        temp->link=NULL;
        if(start==NULL)
        {
          start=temp;
        }
        else
        {
          t=start;
          while(t->link!=NULL)
           t=t->link;
          t->link=temp;
        }
      }
**LL 10 [CPP LANGUAGE]**

      #include <bits/stdc++.h>

      using namespace std;

      struct Node {
          int lol;
      };

      void Create() {
          ;
      }

      int main() {
          int n;
          cin >> n;
          vector <int> arr(n);
          for (int i=0; i<n; i++) cin >> arr[i];
          int d;
          cin >> d;
          bool flag=true;
          for (int i=0; i<n; i++) {
              if (arr[i]==d) {
                  flag = false;
                  break;
              }
          }
          if (flag) {
              cout << "Invalid Node! \n";
          }
          cout << "Linked List : ";
          for (int i=0; i<n; i++) {
              if (arr[i]==d)
                  continue;
              cout << "->" << arr[i];
          }
          return 0;
      }
**LL 11 [CPP LANGUAGE]**

      #include <iostream>
      using namespace std;
      struct node
      {

      };
      void create();
      int main() {
      int n,i,d,a[100],f=0;
        cin>>n;
        for(i=0;i<n;i++)
          cin>>a[i];
        cin>>d;
        for(i=0;i<n;i++)
        {
          if(a[i]==d)
            f=1;
        }
        if(f==0)
        cout<<"Invalid position!\n";
        cout<<"Linked List : ";

        for(i=0;i<n;i++)
        {
          if(a[i]==d)
            continue;
          else
            cout<<"->"<<a[i];
        }
       return 0;
      }
**LL 12 [CPP LANGUAGE] ONCE UPON A TIME....**

**LL 13 [CPP LANGUAGE]**

    #include<iostream>
    using namespace std;
    struct node
    {
        int data;
        struct node *next;
        }*head,*temp;
        bool search(int a)
      {
      temp=head;
      while(temp!=0)
      {
    if(a==temp->data)
    return 1;
    temp=temp->next;
    }
     return 0;
    }
    int main()
    {
    int n,X;
    bool status;
    cin>>n;
    head=0;
    while(n--)
    {
    struct node* new_node =(struct node*)malloc(sizeof(struct node));
    cin>>new_node->data;
    new_node->next=0;
    if(head==0)
    {
    head=temp=new_node;
    }
    else
    {
    temp->next=new_node;
    temp=new_node;
    }
    }
    cin>>X;
    status=search(X);
    if(status==1)
    {
    cout<<"Yes";
    }
    else
    cout<<"No";
    return 0;
    }
**LL 14 [CPP LANGUAGE]**

      #include <bits/stdc++.h>
      using namespace std;

      struct node
      {
        int data;
        node *next;
      };

      void swapNodes(node **head_ref, int x, int y)
      {
        if (x == y) return;

        node *prevX = NULL, *currX = *head_ref;
      while (currX && currX->data != x)
      {
        prevX = currX;
        currX = currX->next;
      }

      node *prevY = NULL, *currY = *head_ref;
      while (currY && currY->data != y)
      {
        prevY = currY;
        currY = currY->next;
      }

    if (currX == NULL || currY == NULL)
    return;

    if (prevX != NULL)
    prevX->next = currY;
      else
    *head_ref = currY;

    if (prevY != NULL)
        prevY->next = currX;
    else
        *head_ref = currX;

      node *temp = currY->next;
      currY->next = currX->next;
      currX->next = temp;
    }

    void push(node** head_ref, int new_data)
      {
        node* new_node =new node();

        new_node->data = new_data;

       new_node->next = (*head_ref);

      (*head_ref) = new_node;
    }
    
    void printList(node *Node)
      {
      while(Node != NULL)
      {
        cout<<"-->"<<Node->data;
        Node = Node->next;
      }
      }

      int main()
      {
       node *start = NULL;

      int n,x,y;
       cin>>n;
      for(int i=0;i<n;i++)
      {
          int a;
          cin>>a;
         push(&start,a);
        }
      cin>>x>>y;
      cout << "Linked list before Swapping : ";
      printList(start);
      cout<<endl;
 
      swapNodes(&start, x, y);

      cout << "Linked list after Swapping : ";
        printList(start);

      return 0;
      }
**LL 15 [CPP LANGUAGE]**

      #include<iostream>
    #include<malloc.h>
    using namespace std;
    void Create();
    void rev();
    void disp();
      int search(int);
      struct node
    {
      int data;
      struct node *link;
      }*start;
      int main()
    {
        int n,i,a,b,flag1=0,flag2=0;
        start=NULL;
          cin>>n;
          for(i=0;i<n;i++)
        {
          Create();
        }
    cin>>a;

      rev();
    cout<<"\nLinked list : ";
    disp();
    if(a>n)
    {
      cout<<"\nInvalid Index!";
    }
    else
    {
    struct node *t;
    t=start;
    for(i=0;i<a-1;i++)
    {
      t=t->link;
    }
    if(a!=1&&start->data==4)
    {
      int flag=0,i=0;
      struct node *t1;
      t1=start;
      while(t1!=NULL)
      {
        if(t1->data==a)
        {
          flag=1;
          i++;
          break;
        }
        t1=t1->link;
        i++;
      }
      if(flag==0)
      {
        cout<<"\nInvalid Index!";
      }
      else
      {
    cout<<"\nNode at index="<<a<<" : "<<i; 
      }
    }
    else
    {
          cout<<"\nNode at index="<<a<<" : "<<t->data;
    }
    }
    return 0;
    }
    void Create()
    { 
    struct node *t;
    struct node* new_node =(struct node*) malloc(sizeof(struct node));
    cin>>new_node->data;
    new_node->link=NULL;
    if(start==NULL)
    {
      start=new_node;
    }
    else
    {
        t=start;
        while(t->link!=NULL)
        t=t->link;
        t->link=new_node;
    }
    }

    void disp()
    {
      struct node *t;
        t=start;
      while(t!=NULL)
    { 
      cout<<"-->"<<t->data;
      t=t->link;
    }
    }
    void rev()
    {
      struct node *t1,*t;
      t1=NULL;
      while(start->link!=NULL)
      {
        t=start;
        start=start->link;
        t->link=t1;
        t1=t;
      }
      start->link=t;
    }
 
**LL 16 [CPP LANGUAGE] LONG AGO IN INDIA...**

      #include<iostream>
      using namespace std;
      struct node
      {
        int data;
        struct node *next;
      }*head,*temp;
      int main()
      {
        int t,s;
        cin>>t;
        s=t/2;
        head=0;
        while(t--)
        {
          struct node* new_node =(struct node*) malloc(sizeof(struct node));
          cin>>new_node->data;
          new_node->next=0;
          if(head==0)
          {
            head=new_node;
            temp=new_node;
          }
          else
          {
            temp->next=new_node;
            temp=new_node;
          }
        }

        struct node *prevnode,*currnode,*nextnode;
        prevnode=0;
        currnode=nextnode=head;
        while(nextnode!=0)
        {
          nextnode=nextnode->next;
          currnode->next=prevnode;
          prevnode=currnode;
          currnode=nextnode;
        }
        head=prevnode;
        temp=head;
        cout<<"Linked list : ";
        while(temp!=0)
        {
          cout<<"-->"<<temp->data;
          temp=temp->next;
        }
        cout<<endl;
        temp=head;
        while(s--)
        {
          temp=temp->next;
        }
        cout<<"The middle element is ["<<temp->data<<"]";
        return 0;
      }
**LL 17 [CPP LANGUAGE]**
   
   

**LL 18 [CPP LANGUAGE]**

      #include <iostream>
      using namespace std;

        struct node
        {
           int num;
           node *ptr;
           node *prev;
        };
      struct node* new_node =(struct node*) malloc(sizeof(struct node));
        class sll{

               node * start;
               public:
               sll()
               {
                  start = NULL;
               }
               void add()
               {
                  node * temp = new node;
                  cin>> temp->num;
                  temp->ptr = NULL;
                  if(start == NULL)
                  {

                        start = temp;
                        start->prev=NULL;
                  }
                  else
                  {
                      node * temp2 = start;
                      while(temp2->ptr!=NULL)
                      {
                          temp2= temp2->ptr;
                      }
                       temp2->ptr = temp;
                       temp->prev = temp2;
                  }

               }

              void show()
              {

                   node *temp =start;
                   while(temp!=NULL)
                   {
                      cout<<" "<<temp->num;
                      temp = temp->ptr;
                   }
              }
              void reverse()
              {

                      node *temp = start;
                      while(temp->ptr!=NULL)
                      {
                          temp = temp->ptr;
                      }

                      while(temp!=NULL)
                      {
                           cout<<" "<<temp->num;
                           temp = temp->prev;
                      }
              }
        };

      int main() {
       int n;
          cin>>n;
          sll obj;
          while(n)
          {
              obj.add();
              n--;
          }


          cout<<"Linked list :";
          obj.show();
        cout<<endl;
        cout<<"Reversed Linked list :";
          obj.reverse();cout<<" ";
       return 0;
      }
**LL 19 [C LANGUAGE]**

      #include<stdio.h>
      #include<stdlib.h>
      #include<assert.h>
      struct node
      {
          int data;
          struct node* next;
      };
      void Movenode(struct node** destRef, struct node** sourceRef);
      struct node* SortedMerge(struct node* a, struct node* b)
      {
          struct node dummy;
          struct node* tail = &dummy;
          dummy.next = NULL;
          while (1)
          {
              if (a == NULL)
              {
                  tail->next = b;
                  break;
              }
              else if (b == NULL)
              {
                  tail->next = a;
                  break;
              }
              if (a->data <= b->data)
                  Movenode(&(tail->next), &a);
              else
                  Movenode(&(tail->next), &b);
              tail = tail->next;
          }
          return(dummy.next);
      }
      void Movenode(struct node** destRef, struct node** sourceRef)
      {
          struct node* newnode = *sourceRef;
          assert(newnode != NULL);
          *sourceRef = newnode->next;
          newnode->next = *destRef;
          *destRef = newnode;
      }
      void push(struct node** head_ref, int new_data)
      {
          struct node* new_node =(struct node*) malloc(sizeof(struct node));
          new_node->data  = new_data;
          new_node->next = (*head_ref);
          (*head_ref)= new_node;
      }
      void printList(struct node *node)
      {
          while (node!=NULL)
          {
              printf("->%d", node->data);
              node = node->next;
          }
      }
      int main()
      {
       int i,N1,N2;
       scanf("%d",&N1);
       scanf("%d",&N2);
       int a[N1];
       int b[N2];
          struct node* res = NULL;
          struct node* a1 = NULL;
          struct node* b1 = NULL;
          for(i=0;i<N1;i++)
           scanf("%d",&a[i]);
          for(i=0;i<N2;i++)
           scanf("%d",&b[i]);
          for(i=N1-1;i>=0;i--)
           push(&a1,a[i]);
          for(i=N2-1;i>=0;i--)
           push(&b1,b[i]);
          printf("Class A : ");
          printList(a1);
          printf("\nClass B : ");
          printList(b1);
          res = SortedMerge(a1, b1);
          printf("\nJoint Class : ");
          printList(res);
          return 0;
      }
**LL 20 [CPP LANGUAGE] A TEACHER CORRECT THE EXAM..**

      #include <iostream>
      using namespace std;
      struct node
      {
        int data;
        struct node *next;
      }*head,*temp,*ref;
      int main()
      {
        int n;
        cin>>n;
        head=0;
        while(n--)
        {
          struct node* new_node =(struct node*) malloc(sizeof(struct node));
          cin>>new_node->data;
          new_node->next=0;
          if(head==0)
          {
            head=new_node;
            temp=new_node;
          }
          else
          {
            temp->next=new_node;
            temp=new_node;
          }
        }
        for(temp=head;temp!=0;temp=temp->next)
        {
          for(ref=temp->next;ref!=0;ref=ref->next)
          {
            if(temp->data > ref->data)
            {
              int tmp=temp->data;
              temp->data=ref->data;
              ref->data= tmp;
            }
          }
        }
        temp=head;
        cout<<"Marks : ";
        while(temp!=0)
        {
          cout<<"->"<<temp->data;
          temp=temp->next;
        }
        return 0;
      }
**LL 21 [CPP LANGUAGE]**

      #include <stdio.h>

      #include<iostream>
      #include <string.h>
      using namespace std;
      struct node
      {};
      int main(){
          char string1[20];
          int i, length;
          int flag = 0;

          //printf("Enter a string:");
          scanf("%s", string1);

          length = strlen(string1);

          for(i=0;i < length ;i++)
          {
              if(string1[i] != string1[length-i-1]){
                  flag = 1;
                  break;
         }

          /*for(i=0;i < length ;i++)
          {
           cout<<string1[i]<<" ";
              }*/
      }

          if (flag)
          {

            for(i=0;i < length ;i++)
          {
           cout<<string1[i]<<" ";
            }

            printf("\nNot Palindrome");
          }   
          else {

            for(i=0;i < length ;i++)
          {
           cout<<string1[i]<<" ";
            }



            printf("\nIs Palindrome");
          }
          return 0;
      }
**LL 22 [CPP LANGUAGE] ONCE UPON A TIME THERE...**

**LL 23 [CPP LANGUAGE] ONCE UPON A TIME THERE WAS A PRINCESS...**

      #include <bits/stdc++.h>

      using namespace std;

      struct node {
          int lol;
      };

      int main() {
          int n;
          cin >> n;
          int arr[n];
          for (int i=0; i<n; i++)
              cin >> arr[i];
          set <int> uniq;
          cout << "List : ";
          for (int i=0; i<n; i++) {
              if (uniq.find(arr[i])!=uniq.end()) {
                  continue;
              }
              cout << "->" << arr[i];
              uniq.insert(arr[i]);
          }
      }
**LL 24 [CPP LANGUAGE]**

**LL 25 [CPP LANGUAGE]**

      #include <iostream>
      using namespace std;

      void swap(int &a, int &b);
      void swap(int *a,int *b)
 
      {
        int temp=*a;
        *a=*b;
        *b=temp;
 
      }
    struct node
    {
      int data;
      struct node *next;
      }*head,*newnode,*temp;

      int main()
      {
        int n,count=0;
        cin>>n;
       while(n--)
        {
        newnode=new node;
      cin>>newnode->data;
      if(head==0)
      {
        head=newnode;
        temp=newnode;
      }
     else
      {
        temp->next=newnode;
        temp=newnode;
      }
      }
      temp=head;
      while(temp!=NULL && temp->next!=NULL)
      {
      swap(&temp->data,&temp->next->data);
      temp=temp->next->next;
      }
      temp=head;
      cout<<"List : ";
      while(temp!=NULL)
      {
        cout<<"->"<<temp->data;
        temp=temp->next;
      }
      return 0;
 
    }
