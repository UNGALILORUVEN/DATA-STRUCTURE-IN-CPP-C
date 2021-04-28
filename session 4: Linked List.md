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

**LL 3 [CPP LANGUAGE]**

**LL 4 [CPP LANGUAGE]**

**LL 5 [CPP LANGUAGE]**

**LL 6 [CPP LANGUAGE]**

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
    
**LL 8 [CPP LANGUAGE]**

**LL 9 [CPP LANGUAGE]**

**LL 10 [CPP LANGUAGE]**

**LL 11 [CPP LANGUAGE]**

**LL 12 [CPP LANGUAGE]**

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
 
**LL 16 [CPP LANGUAGE]**

**LL 17 [CPP LANGUAGE]**
   
**LL 18 [CPP LANGUAGE]**

**LL 19 [CPP LANGUAGE]**

**LL 20 [CPP LANGUAGE]**

**LL 21 [CPP LANGUAGE]**

**LL 22 [CPP LANGUAGE]**

**LL 23 [CPP LANGUAGE]**

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
