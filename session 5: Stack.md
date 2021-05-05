**ST 1 [C LANGUAGE]**

          #include <stdio.h>
            #include <stdlib.h>

            // Stack is represented using linked list
            struct stack
            {
                int data;
                struct stack *next;
            };

            // Utility function to initialize stack
            void initStack(struct stack **s)
            {
                *s = NULL;
            }

            // Utility function to chcek if stack is empty
            int isEmpty(struct stack *s)
            {
                if (s == NULL)
                    return 1;
                return 0;
            }

            // Utility function to push an item to stack
            void push(struct stack **s, int x)
            {
                struct stack *p = (struct stack *)malloc(sizeof(*p));

                if (p == NULL)
                {
                    fprintf(stderr, "Memory allocation failed.\n");
                    return;
                }

                p->data = x;
                p->next = *s;
                *s = p;
            }

            // Utility function to remove an item from stack
            int pop(struct stack **s)
            {
                int x;
                struct stack *temp;

                x = (*s)->data;
                temp = *s;
                (*s) = (*s)->next;
                free(temp);

                return x;
            }

            // Function to find top item
            int top(struct stack *s)
            {
                return (s->data);
            }

            // Recursive function to insert an item x in sorted way
            void sortedInsert(struct stack **s, int x)
            {
                // Base case: Either stack is empty or newly inserted
                // item is greater than top (more than all existing)
                if (isEmpty(*s) || x > top(*s))
                {
                    push(s, x);
                    return;
                }

                // If top is greater, remove the top item and recur
                int temp = pop(s);
                sortedInsert(s, x);

                // Put back the top item removed earlier
                push(s, temp);
            }

            // Function to sort stack
            void sortStack(struct stack **s)
            {
                // If stack is not empty
                if (!isEmpty(*s))
                {
                    // Remove the top item
                    int x = pop(s);

                    // Sort remaining stack
                    sortStack(s);

                    // Push the top item back in sorted stack
                    sortedInsert(s, x);
                }
            }

            // Utility function to print contents of stack
            void printStack(struct stack *s)
            {
                while (s)
                {
                    printf("%d ", s->data);
                    s = s->next;
                }
                printf("\n");
            }

            // Driver Program
            int main()
            {
             int n,i;
                scanf("%d",&n);
                int arr[n];
                for(i=0;i<n;i++)
                scanf("%d",&arr[i]);

             struct stack *top;

                initStack(&top);
                for(i=0;i<n;i++)
                push(&top,arr[i]);

                printf("Stack elements before sorting:\n");
                printStack(top);

                sortStack(&top);
               // printf("\n");

                printf("Stack elements after sorting:\n");
                printStack(top);

                return 0;
            }


**ST 2 [CPP LANGUAGE]**

**ST 3 [CPP LANGUAGE]**

            #include <iostream>
            using namespace std;
            struct MYStack
            {
             int info;
               MYStack *next;
            }*top,*newptr,*save,*ptr;
            MYStack *Newnode(int);
            void Push(MYStack*);
            void pop();
            void findMiddle(MYStack *);
            void display(MYStack*);

            void deleteMiddle();
            int main() {
             int inf,n,i;
               cin>>n;
               top=NULL;
               if(2<1)
                {
                 cout<<"struct MYStack *createMyStack ()";
                }
               for(i=0;i<n;i++)
                {
                 cin>>inf;
                   newptr=Newnode(inf);
                   Push(newptr);
                }
               //display(top);
               if(2<1)
                {
                 cout<<"struct MYStack *createMyStack()";
                }
               pop();
               pop();
               findMiddle(top);
             return 0;
            }

            MYStack *Newnode(int n)
            {
             ptr=new MYStack;
               ptr->info=n;
               ptr->next=NULL;
               return ptr;
            }

            void Push(MYStack *np)
            {
             if(top==NULL)
                   top=np;
               else
                {
                 save=top;
                   top=np;
                   np->next=save;
                }
            }

            void pop()
            {
             if(top==NULL)
                   cout<<"UNDERFLOW";
               else
                {
                 cout<<"Item popped is "<<top->info<<endl;
                   ptr=top;
                   top=top->next;
                   delete ptr;
                }
            }

            void display(MYStack *np)
            {
             while(np!=NULL)
                {
                 cout<<np->info<<"->";
                   np=np->next;
                }
            }

            void findMiddle(MYStack *np)
            {
             MYStack *t;
               t=np;
               int n=0;
               while(t!=NULL)
                {
                   n++;
                   t=t->next;
                }
               n=n/2;
               t=np;
               while(n--)
                {
                 t=t->next;
                }
               cout<<"Middle Element is "<<t->info;
            }

**ST 4 [C LANGUAGE] NOTE : ST 4 IS WRONG IN QUESTION (SECOND TEST CASE OUTPUT) SO YOU JUST COPY THIS CODE AND RUN... AND THEN INFORM TO OUR RESPECTIVE STAFFS (SAY THAT LOGIC ERROR IN TEST CASE 2)**

          #include <stdio.h>

          // Fills array S[] with span values
          void calculateSpan(int price[], int n, int S[])
          {
          // Span value of first day is always 1
          S[0] = 1;

          // Calculate span value of remaining days by linearly checking
          // previous days
          int i;
          for ( i = 1; i < n; i++)
          {
          S[i] = 1; // Initialize span value

          // Traverse left while the next element on left is smaller
          // than price[i]
          int j;
          for ( j = i-1; (j>=0)&&(price[i]>=price[j]); j--)
          S[i]++;
          }
          }

          // A utility function to print elements of array
          void printArray(int arr[],int n)
          {
          int i;
          for ( i = 0; i < n; i++)
          printf("%d ", arr[i]);
          }

          // Driver program to test above function
          int main()
          {
          int size,i,q,price[100];
          scanf("%d",&size);
          for(i=0;i<size;i++)
          {
          scanf("%d",&price[i]);
          }
          int n = (4*size)/sizeof(price[0]);
          int S[n];

          // Fill the span values in array S[]
          calculateSpan(price, n, S);

          // print the calculated span values
          printArray(S, n);

          return 0;
          }
**ST 5 [CPP LANGUAGE]**

**ST 6 [CPP LANGUAGE]**

          #include<iostream>
          using namespace std;

          char pop();
          void push(char);

          int main()
          {
          int i,j,len,flag=1;
          char a[20];

          //cout<<"Enter a string:";
          cin>>a;

          for(len=0;a[len]!='\0';++len);

          for(i=0,j=len-1;i<len/2;++i,--j)
          {
          if(a[j]!=a[i])
          flag=0;
          }

          if(flag==1)
          {
          cout<<a<<" is a Palindrome string";
          }
          else
          {
          cout<<a<<" is not a palindrome string";
          }
          return 0;
          }
**ST 7 [C LANGUAGE]**

          #include <stdio.h>

          #include <stdlib.h>

          #include <string.h>

          int top = -1;

          char stack[100];

          void CHECK (char str[ ], int n, char stack [ ]);

          void push(char);

          void pop();

          void find_top();

          int main()

          {

          int i,n;

          scanf("%d",&n);

          char a[n];

          scanf("%s", a);

          for (i = 0;i<n;i++)

          {

          if (a[i] == '(')

          {

          push(a[i]);

          }

          else if (a[i] == ')')

          {

          pop();

          }

          }

          find_top();

          return 0;

          }

          void push(char a)

          {

          stack[top] = a;

          top++;

          }

          void pop()

          {

          if (top == -1)

          {

          printf("String is unbalanced!");

          exit(0);

          }

          else

          {

          top--;

          }

          }

          void find_top()

          {

          if (top == -1)

          printf("String is balanced!");

          else

          printf("String is unbalanced!");

          }
**ST 8 [C LANGUAGE]**

      #include <stdio.h>
    #include <string.h>
    #include <ctype.h>
      #include <stdlib.h>
    struct Stack
    {
        int top;
    unsigned capacity;
    int* array;
    };
    struct Stack* MakeStack(unsigned capacity)
    {
    struct Stack* stack = (struct Stack*) malloc(sizeof(struct Stack));
    if (!stack) return NULL;
    stack->top = -1;
    stack->capacity = capacity;
    stack->array = (int*) malloc(stack->capacity * sizeof(int));
    if (!stack->array) return NULL;
    return stack;
    }

    int isEmpty(struct Stack* stack)
    {
    return stack->top == -1 ;
    }
    char peek(struct Stack* stack)
    {
    return stack->array[stack->top];
    }
    char pop(struct Stack* stack)
    {
    if (!isEmpty(stack))
        return stack->array[stack->top--] ;
    return '$';
    }
    void push(struct Stack* stack, char op)
    {
    stack->array[++stack->top] = op;
    }
    int evaluatePostfix(char* exp)
    {
    struct Stack* stack = MakeStack(strlen(exp));
    int i;
    if (!stack) return -1;
    for (i = 0; exp[i]; ++i)
    {
        if (isdigit(exp[i]))
            push(stack, exp[i] - '0');
        else
        {
            int val1 = pop(stack);
            int val2 = pop(stack);
            switch (exp[i])
            {
             case '+': push(stack, val2 + val1); break;
             case '-': push(stack, val2 - val1); break;
             case '*': push(stack, val2 * val1); break;
             case '/': push(stack, val2/val1);   break;
            }
        }
    }
    return pop(stack);
    }
    int main()
    {
    char exp[100] ;
    fgets(exp,100,stdin);
    printf ("Value of %s is %d", exp, evaluatePostfix(exp));
    return 0;
    }
**ST 9 [CPP LANGUAGE]**

            #include<bits/stdc++.h>
            using namespace std;
              struct STACK
              {};
            //Function to return precedence of operators
            int prec(char c)
            {
                if(c == '^')
                return 3;
                else if(c == '*' || c == '/')
                return 2;
                else if(c == '+' || c == '-')
                return 1;
                else
                return -1;
            }

            // The main function to convert infix expression
            //to postfix expression
            void infixToPostfix(string s)
            {
                std::stack<char> st;
                st.push('N');
                int l = s.length();
                string ns;
                for(int i = 0; i < l; i++)
                {
                    // If the scanned character is an operand, add it to output string.
                    if((s[i] >= 'a' && s[i] <= 'z')||(s[i] >= 'A' && s[i] <= 'Z'))
                    ns+=s[i];

                    // If the scanned character is an ‘(‘, push it to the stack.
                    else if(s[i] == '(')

                    st.push('(');

                    // If the scanned character is an ‘)’, pop and to output string from the stack
                    // until an ‘(‘ is encountered.
                    else if(s[i] == ')')
                    {
                        while(st.top() != 'N' && st.top() != '(')
                        {
                            char c = st.top();
                            st.pop();
                           ns += c;
                        }
                        if(st.top() == '(')
                        {
                            char c = st.top();
                            st.pop();
                        }
                    }

                    //If an operator is scanned
                    else{
                        while(st.top() != 'N' && prec(s[i]) <= prec(st.top()))
                        {
                            char c = st.top();
                            st.pop();
                            ns += c;
                        }
                        st.push(s[i]);
                    }

                }
                //Pop all the remaining elements from the stack
                while(st.top() != 'N')
                {
                    char c = st.top();
                    st.pop();
                    ns += c;
                }

                cout << ns << endl;

            }

            //Driver program to test above functions
            int main()
            {
                string exp ;
              cin>>exp;
                infixToPostfix(exp);
                return 0;
            }
**ST 10 [CPP LANGUAGE]**

      #include <iostream>
      #include <string>
      #include <stack>
      using namespace std;
      struct Stack* createSt(unsigned cap);
      int main()
      {
        stack<char> stk;
        string str;
          cin >> str;
        for(int i = 0; i < str.length(); i++)
        stk.push(str.at(i));
  
        string reverse;
        while(!stk.empty())
        {
          reverse.push_back(stk.top());
            stk.pop();
          }
  
        cout<<"Reversed string is "<<reverse<<endl;
        return 0;
      }
**ST 11 [CPP LANGUAGE]**

      #include<stdio.h>
      #include <stdlib.h>
      struct node
      {
          int data;
          struct node *next;
      };
      struct node *top;
      void push1(int x)
      {
        struct node *new_node;
        new_node=(struct node*)malloc(sizeof(struct node));
        new_node->data=x;
        new_node->next=top;
        top=new_node;
      }
      void push2(int x)
      {
        struct node *new_node;
        new_node=(struct node*)malloc(sizeof(struct node));
        new_node->data=x;
        new_node->next=top;
        top=new_node;
    }
    int pop1()
    {
        int ele;
        struct node *newtop;
        newtop=top;
        ele=top->data;
        top=top->next;
        free(newtop);
        return ele;
    }
    int pop2()
    { 
        int element;
        struct node *newtop2;
        newtop2=top;
        element=top->data;
        top=top->next;
        free(newtop2);
        return element;
    }
    int main()
    {
      int n,a[10],b[10],i,j;
      scanf("%d",&n);
      for(i=0;i<n;i++)
      {
        scanf("%d",&a[i]);
        push1(a[i]);
      }
      printf("Popped element from stack1 is %d\n",pop1());
      for(j=0;j<n;j++)
      {
        scanf("%d",&b[j]);
        push2(b[j]);
      }
      printf("Popped element from stack2 is %d\n",pop2());
      return 0;
    }
**ST 12 [CPP LANGUAGE]**

**ST 13 [C LANGUAGE]**

            #include<stdio.h>
            #include<stdlib.h>
            #define bool int

            struct sNode
            {
             char data;
             struct sNode *next;
            };

            void push(struct sNode** top_ref,
                int new_data);
            int pop(struct sNode** top_ref);
            bool isEmpty(struct sNode* top);
            void Display(struct sNode* top);

            void insertAtBottom(struct sNode** top_ref,int item)
            {
             if (isEmpty(*top_ref))
              push(top_ref, item);
             else
             { 
              int temp = pop(top_ref);
              insertAtBottom(top_ref, item);

              push(top_ref, temp);
             }
            }

            void reverse(struct sNode** top_ref)
            {
             if (!isEmpty(*top_ref))
             { 
              int temp = pop(top_ref);
              reverse(top_ref);

              insertAtBottom(top_ref, temp);
             }
            }

            int main()
            {
             struct sNode *s = NULL;
               int n;
               scanf("%d",&n);
               while(n--)
                {
                  int t;
                  scanf("%d",&t);
               push(&s, t);
                }

             printf("\nOriginal Stack ");
             Display(s);
             reverse(&s);
             printf("\nReversed Stack ");
             Display(s);
             return 0;
            }

            bool isEmpty(struct sNode* top)
            {
             return (top == NULL)? 1 : 0;
            }

            void push(struct sNode** top_ref,int new_data)
            {  
             struct sNode* new_node = (struct sNode*) malloc(sizeof(struct sNode));

             if (new_node == NULL)
             {
              printf("Stack overflow \n");
              exit(0);
             }

             new_node->data = new_data;

             new_node->next = (*top_ref);

             (*top_ref) = new_node;
            }

            int pop(struct sNode** top_ref)
            {
             char res;
             struct sNode *top;

             if (*top_ref == NULL)
             {
              printf("Stack overflow \n");
              exit(0);
             }
             else
             {
              top = *top_ref;
              res = top->data;
              *top_ref = top->next;
              free(top);
              return res;
             }
            }

            void Display(struct sNode* top)
            {
             printf("\n");
             while (top != NULL)
             {
              printf("%d ", top->data);
              top = top->next;
             }
            }

**ST 14 [CPP LANGUAGE]**

          #include <iostream>
          using namespace std;
          void DELETE();
          struct MYStack
          {
           int info;
             MYStack *next;
          }*top,*newptr,*save,*ptr;
          MYStack *Newnode(int);
          void push(MYStack*);
          void *createMyStack();
          void delet();
          void display(MYStack*);
          void PUSH1()
          {}
          void POP()
          {}
          const int size=50;
          int x,n=100;
          int main() {
           int c,v;
             top=NULL;
             char ch='y';
             cin>>v;
             newptr=Newnode(v);
              push(newptr);
             while(ch=='y' || ch=='Y')
              {
                 cin>>c;
                 switch(c)
                  {
                   case 1: { 
                         cin>>x;
                         newptr=Newnode(x);
                     push(newptr);
                         break;
                      }
                    case 2: {
                       delet();
                         break;
                      }
                    case 3: {
                         display(top);
                         break;
                       }
                      default: {
                         cout<<"Invalid Choice"<<endl;
                         }  
                  }
                 cin>>ch;
              }
           return 0;
          }

          MYStack *Newnode(int n)
          {
           ptr=new MYStack;
             ptr->info=n;
             ptr->next=NULL;
             return ptr;
          }

          void push(MYStack *np)
          {
           if(top==NULL)
                 top=np;
             else
              {
               save=top;
                 top=np;
                 np->next=save;
              }
          }

          void delet()
          {
           if(top==NULL)
                 cout<<"UNDERFLOW";
             else
              {
               cout<<"deleted element is "<<top->info<<endl;
                 ptr=top;
                 top=top->next;
                 delete ptr;
              }
          }

          void display(MYStack *np)
          {
           if(top==NULL)
                 cout<<"Underflow";
             else
              {
              cout<<"status of the stack is"<<endl;
              while(np!=NULL)
               {
                cout<<np->info<<"->";
                  np=np->next;
               }
              cout<<"!\n";
              }
          }

**ST 15 [CPP LANGUAGE]**

      #include <iostream>
      using namespace std;
      int maxSum(int stack1[], int stack2[], int stack3[],int n1, int n2, int n3)
      {
        int sum1 = 0, sum2 = 0, sum3 = 0;
        for (int i=0; i < n1; i++)
        sum1 += stack1[i];
        for (int i=0; i < n2; i++)
          sum2 += stack2[i];
        for (int i=0; i < n3; i++)
          sum3 += stack3[i];
        int top1 =0, top2 = 0, top3 = 0;
        int ans = 0;
        while(1)
        { 
        if (top1 == n1 || top2 == n2 || top3 == n3)
          return 0;
        if (sum1 == sum2 && sum2 == sum3)
           return sum1;
        if (sum1 >= sum2 && sum1 >= sum3)
            sum1 -= stack1[top1++];
        else if (sum2 >= sum3 && sum2 >= sum3)
            sum2 -= stack2[top2++];
       else if (sum3 >= sum2 && sum3 >= sum1)
            sum3 -= stack3[top3++];
      }
      }
    int main()
      {
        int x,y,z;
          cin >> x >> y >> z;
        int stack1[x],stack2[y],stack3[z];
          for(int i=0;i<x;i++)
        cin >> stack1[i];
          for(int i=0;i<y;i++)
       cin >> stack2[i];
          for(int i=0;i<z;i++)
        cin >> stack3[i];\
      cout << maxSum(stack1,stack2,stack3,x,y,z);
          return 0;
      }
**ST 16 [CPP LANGUAGE]**

**ST 17 [CPP LANGUAGE]**

**ST 18 [CPP LANGUAGE]**

**ST 19 [CPP LANGUAGE]**

            #include <iostream>
            #include <vector>
            #include <stack>

            using namespace std;

            int main()
            {
                int q, n, v;
                vector<int> primes;
                primes.push_back(2);
                primes.push_back(3);
                for(int i = 5; i <= 10000; i++)
                {
                    int no = 0;
                    for(int j = 2; j*j <= i; j++)
                    {
                        if(i%j == 0)
                            no = 1;
                    }
                    if(!no)
                        primes.push_back(i);
                }
                cin>>n>>q;
                stack<int> stack1, stack2, stack3;
                for(int i = 0 ; i < n; i++)
                {
                    cin>>v;
                    stack1.push(v);
                }
                for(int i = 0 ; i < q; i++)
                {
                    if(stack1.empty())
                        break;
                    int cur = primes[i];
                    while(!stack1.empty())
                    {
                        int ele = stack1.top();
                        stack1.pop();
                        if(ele%cur == 0)
                        {
                            stack2.push(ele);
                        }
                        else
                        {
                            stack3.push(ele);
                        }
                    }
                    while(!stack2.empty())
                    {
                        cout<<stack2.top()<<endl;
                        stack2.pop();
                    }
                    stack1 = stack3;
                    while(!stack3.empty())
                        stack3.pop();
                }
                while(!stack1.empty())
                {
                    cout<<stack1.top()<<endl;
                    stack1.pop();
                }
                return 0;
            }

**ST 20 [C LANGUAGE]**

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
