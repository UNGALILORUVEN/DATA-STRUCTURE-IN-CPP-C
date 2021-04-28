**ST 1 [CPP LANGUAGE]**

**ST 2 [CPP LANGUAGE]**

**ST 3 [CPP LANGUAGE]**

**ST 4 [CPP LANGUAGE]**

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
**ST 7 [CPP LANGUAGE]**

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

**ST 13 [CPP LANGUAGE]**

**ST 14 [CPP LANGUAGE]**

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

**ST 20 [CPP LANGUAGE]**
