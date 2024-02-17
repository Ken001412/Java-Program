# Java-Program
/*PROGRAM FOR BINARY SEARCH*/

import java.io.*;
class binarysearch
  {
    public static void main(String at[])throws Exception
    {
      DataInputStream z=new DataInputStream(System.in);
      int n,x;
      System.out.println("enter the number of elements in array"); // inputting array elements
      n=Integer.parseInt(z.readLine());
      int ar[]=new int[n];
      System.out.println("enter the elements");// inputting array elements

      for(x=0;x<n;x++)
      ar[x]=Integer.parseInt(z.readLine());
      System.out.println("enter the element to be searched");
      int b= Integer.parseInt(z.readLine());
      binarysearch obj=new binarysearch();
      int j=obj.bs(ar,0,n-1,b);
      if(j==1)
        System.out.println("element present"); // printing elements present
      else
        System.out.println("element absent");  // printing elements present

    }
   int bs(int a[],int s,int e,int n)
   {
     if(s>e)
       return 0;
     else
     {
       int m=(s+e)/2;
       if(a[m]==n)
         return 1;
       else
       {
         if(a[m]<n)
           return bs(a,m+1,e,n);
         else
           return bs(a,s,m-1,n);
       }
      }
   }
}
 
enter the number of elements in array
7
enter the elements
2
4
6
9
45
36
14
enter the element to be searched
6
element present
 

/*PROGRAM FOR FINDING NUMBER OF LAMPS IN FARMERS LAND*/

import java.io.*;
import java.util.*;
class farmerslandL
{
public static void main(String kv[])throws Exception
{
    DataInputStream z=new DataInputStream(System.in);
Scanner sc=new Scanner(System.in);
int ro,co,i,j,k,l,r1,c1,r,c,m=0,p=0;
String s;
System.out.println("enter dimensions of array"); // inputting dimensions of array
ro=sc.nextInt();
co=sc.nextInt();
int a[][]=new int[ro][co];
System.out.println("enter no. of lamps"); // inputting number of lamps
l=sc.nextInt();
System.out.println("enter dimensions of cell");
for(i=0;i<ro;i++)
{
for(j=0;j<co;j++)
a[i][j]=0;
}
for(i=1;i<=l;i++)
{
    s=z.readLine();
r=Integer.parseInt(s.substring(0,s.indexOf(',')));
c=Integer.parseInt(s.substring(s.indexOf(',')+1));
if(a[r][c]>=0)
a[r][c]=a[r][c]+10;
if(c+1>=0&&c+1<=co-1)                                                                                              
a[r][c+1]++;
if(r+1>=0&&r+1<=ro-1)                                                                                                 
a[r+1][c]++;
if(c-1>=0&&c-1<=co-1)                                               
a[r][c-1]++;                                                            
if(r-1>=0&&r-1<=ro-1)                                                  
a[r-1][c]++;
if(r-1>=0&&r-1<=ro-1&&c+1>=0&&c+1<=co-1)                               
a[r-1][c+1]++;
if(r+1>=0&&r+1<=ro-1&&c+1>=0&&c+1<=co-1)                                                 
a[r+1][c+1]++;
if(r+1>=0&&r+1<=ro-1&&c-1>=0&&c-1<=co-1)                                                    
a[r+1][c-1]++;
if(r-1>=0&&r-1<=ro-1&&c-1>=0&&c-1<=co-1)                            
a[r-1][c-1]++;
}
for(i=0;i<ro;i++)
{
for(j=0;j<co;j++)
System.out.print(a[i][j]+"\t");
System.out.println();
}
for(r=0;r<ro;r++)
{
    for(c=0;c<co;c++)
    {
        if(a[r][c]>=10)
        {
            if(c+1>=0&&c+1<=co-1)
            {
            if(a[r][c+1]-1<1)
            m++;
        }
            if(r+1>=0&&r+1<=ro-1)
            {
            if(a[r+1][c]-1<1)
            m++;
        }
            if(c-1>=0&&c-1<=co-1)
            {
            if(a[r][c-1]-1<1)
            
        m++;
    }
            if(r-1>=0&&r-1<=ro-1)
            {
            if(a[r-1][c]-1<1)
            m++;
        }
            if(r-1>=0&&r-1<=ro-1&&c+1>=0&&c+1<=co-1)
            {
            if(a[r-1][c+1]-1<1)
            m++;
        }
            if(r+1>=0&&r+1<=ro-1&&c+1>=0&&c+1<=co-1)
            {
            if(a[r+1][c+1]-1<1)
            m++;
        }
            if(r+1>=0&&r+1<=ro-1&&c-1>=0&&c-1<=co-1)
            {
            if(a[r+1][c-1]-1<1)
            m++;
        }
            if(r-1>=0&&r-1<=ro-1&&c-1>=0&&c-1<=co-1)
            {
            if(a[r-1][c-1]-1<1)
            m++;
        }
            if(m>0)
            p++;
            m=0;
}
}
}
System.out.println("no. of useless lamps= "+(l-p)); // printing the number of useless lamps
}
}



















Output :



enter dimensions of array
5
5
enter no. of lamps
6
enter dimensions of cell
1,1
4,4
0,3
1,2
1,3
0,3
1       2       5       22      3
1       11      14      13      3
1       2       3       2       1
0       0       0       1       1
0       0       0       1       10
no. of useless lamps= 3



 
/*PROGRAM FOR CHECKING THE SIZE OF CELLS OF ZOO*/

import java.util.*;
class zoo
{
public static void main(String at[])
{
Scanner sc=new Scanner(System.in);
int x1,x3,y1,y3,n,i,xx1=0,yy1=0,xx3=0,yy3=0,q=0;
System.out.println("enter number of cells");
n=sc.nextInt();
abc: for(i=1;i<=n;i++)
{
System.out.println("enter coordinates of diagonal"); // inputting the coordinates of diagonals
x1=sc.nextInt();
y1=sc.nextInt();
x3=sc.nextInt();
y3=sc.nextInt();
if(x1>xx1&&x1<xx3)
{
if(y1>yy1&&y1<yy3) //checking if valid or not
{
System.out.println("invalid");
break abc;
}
}
else
q++;
if(x3<xx3&&x3>xx1)
{
if(y3<yy3&&y3>yy1)
{
System.out.println("invalid");  // printing the result
break abc;
}
}
else
q++;
xx1=x1;
yy1=y1;
xx3=x3;
yy3=y3;
}
if(q==n*2)
System.out.println("valid");
}
}
 
enter number of cells
4
enter coordinates of diagonal
1
1
2
2
enter coordinates of diagonal
2
4
3
2
enter coordinates of diagonal
3
5
4
2
enter coordinates of diagonal
2
1
5
2
valid











/*PROGRAM TO FIND RUN AROUND NUMBER*/

import java.util.*;
class runaroundnumber
{
public static void main(String kv[])
{
Scanner sc=new Scanner(System.in);
{
int n,l,g,q,i,k,w=0,m=0,s=0,j;
String s1="";
System.out.println("enter a number"); //inputting the number
n=sc.nextInt();
s1=s1+n;
l=s1.length();
int b[]=new int[l];
for(g=0;g<l;g++)
{
q=n%10;
n=n/10;
b[g]=q;
}
int a[]=new int[l];
i=0;
for(k=l-1;k>=0;k--)
{
a[i]=b[k];
i++;
}
i=0;
abc: for(i=0;i<a.length;)
{
j=a[i];
s=j;
if(s>a.length)
{
s=s-a.length;
i=i+s;
}
else
i=i+s;
while(i>=a.length)
i=i-a.length; // checking if number is runaround
m++;
if(m==1)
{
if(a[i]==a[0])
{
System.out.println("IT IS NOT A RUNAROUND NUMBER");
break abc;
}
}
if(m>1)
{
if(m==a.length)
{
if(a[i]==a[0])
{
System.out.println("IT IS A RUNAROUND NUMBER"); //printing result
break abc;
}
else
{
w++;
System.out.println("IT IS NOT A RUNAROUND NUMBER");
break abc;
}
}
}
}
}
}
}
 
enter a number
81362
IT IS A RUNAROUND NUMBER 
/*PROGRAM TO ROTATE A STRINGS*/

import java.util.*;
import java.lang.*;
import java.io.*;
class rotate
{
	public static void main (String[] args) throws java.lang.Exception
	{
		DataInputStream z=new DataInputStream(System.in);
		String s1,s2,s;
		int l,x,count1=1,count2=1;
		System.out.println("Enter two strings"); //inputting two strings
		s1=z.readLine();
		s2=z.readLine();
		s=s2;String s3=s2;
         	l=s1.length();
		if(s1.length()!=s2.length()) 
                 {
                  System.out.println("\n"+"Not Possible");
                  System.exit(0);
                 }
		for(x=0;x<l;x++)
		{
			s=s2.substring(0,l-1);
			s=s2.charAt(l-1)+s;
			
			if(s.equals(s1))
			break;
			else
			count1++;
			s2=s;
		}
		
		s2=s3;
		for(x=0;x<l;x++)
		{
			s=s2.substring(1,l);
			s=s+s2.charAt(0);
		//rotating the strings
			if(s.equals(s1))
			break;
			else
			count2++;
			s2=s;
		}
		
                if(count1==(l+1)&&count2==(l+1))
                System.out.println("\n"+"Not Possible");
                else
		if(count1<=count2)
		System.out.println("\n"+"Right"+"\n"+count1); //printing the rotated strings
		else
		System.out.println("\n"+"Left"+"\n"+count2);
}
}

		
 
Enter two strings
abcde
cdeab

Right
2 
/*SUDOKU GAME MADE IN JAVA*/

import java.io.*;
import java.util.*;
class sudokugame
{
    public static void main(String kv[])throws Exception
    {
        DataInputStream z=new DataInputStream(System.in);
        Scanner sc=new Scanner(System.in);
        char c;
        String s,s1="";
        int i,j=0,k,v=0,m,x=0,y=0,f=3,g=3,b=0,n;
        int a[][]=new int[9][9];
        ka: for(i=0;i<9;i++)
        {                                                                                           //start of i
           s=z.readLine();
for(j=0;j<s.length();j++)
{                                                                                                   //start of j
c=s.charAt(j);
if(c!=',')
s1=s1+c;
}                                                                                                    //end of j
 for(n=0;n<s1.length();n++)
 {                                                                                                  //start of n
     a[i][n]=Integer.parseInt(""+s1.charAt(n));
    }                                                                                               //end of n
    if(s1.length()>9)
    {                                                                                               //start of if
        b++;
        System.out.println("invalid");
        break ka;
    }                                                                                               //end of if
    else
    s1="";
}                                                                                                   //end of i
if(b==0)
{                                                                                                   //start of if
    rt: for(i=0;i<9;i++)
    {                                                                                              //start of i
        for(k=1;k<=9;k++)
        {                                                                                         //start of j
            for(j=0;j<9;j++)
            {                                                                                       //start of k
                if(k==a[i][j])
                v++;
            }                                                                                       //end of k
            if(v>1)
            {                                                                                       //start of if
                b++;
                System.out.println("invalid");
                break rt;
            }                                                                                        //end of if
            else
            v=0;
        }                                                                                           //end of j
    }                                                                                               //end of i
}                                                                                                   //end of if
//System.out.println("valid");
v=0;
if(b==0)
{                                                                                                   //start of if
    ik: for(i=0;i<9;i++)
    {                                                                                               //start of i
        for(k=1;k<=9;k++)
        {                                                                                           //start of j
            for(j=0;j<9;j++)
            {                                                                                      //start of k
                if(k==a[j][i])
                v++;
            }                                                                                       //end of k
            if(v>1)
            {                                                                                       //start of if
                b++;
                System.out.println("invalid");
                break ik;
            }                                                                                       //end of if
            else
            v=0;
        }                                                                                           //end of j
    }                                                                                               //end of i
}                                                                                                   //end of if
//System.out.println("valid");
v=0;
if(b==0)
{                                                                                                   //start of if
    abc: for(m=1;m<=9;m++)
    {                                                                                               //start of m
        //System.out.println("m==========="+m);
        if(m==4)
        {
            x=3;
            f=6;
        }
         if(m==4)
            {//System.out.println("invalid 1");
                y=0;
                g=3;
            }
        for(i=x;i<f;i++)
        {                                                                                               //start of i
            for(j=y;j<g;j++)
            {                                                                                           //start of j
                for(k=1;k<=9;k++)
                {                                                                                       //start of k
                    if(a[i][j]==k)
                    v++;
                }                                                                                       //end of k
                if(v>1)
                {                                                                                       //start of if
                    b++;
                    System.out.println("invalid");
                    break abc;
                }                                                                                        //end of if
                else
                v=0;
            }                                                                                               //end of j
        }                                                                                                   //end of i
        if(m<=3)
        {
            if(j==g)
            {
                y=g;
                g=g+3;
            }
        }
        else if(m>=4&&m<=6)
        {
            
                x=3;
                f=6;
            
            if(m==4)
            {//System.out.println("invalid 1");
                y=0;
                g=3;
            }
            else
            {
                if(j==g)
                {
                    //System.out.println("invalid 2");
                y=g;
                g=g+3;
            }
        }
        }
        else if(m>=7&&m<=9)
        {
            
                x=6;
                f=9;
            
            if(m==7)
            {
                y=0;
                g=3;
            }
            else
            {
                y=g;
                g=g+3;
            }
        }
    }                                                                                                               //end of m
}                                                                                                                   //end of if
        if(b==0)
        System.out.println("valid");
    }
}
 
8,2,7,1,5,4,3,9,6
9,6,8,3,2,7,1,4,5
3,4,1,6,8,9,7,5,2
5,9,3,4,6,8,2,7,1
4,7,2,5,1,3,6,8,9
6,1,8,9,7,2,4,3,5
7,8,6,2,3,5,9,1,4
1,5,4,7,9,6,8,2,3
2,3,9,8,4,1,5,6,7
Invalid























/*PROGRAM TO SHOW QUEUE*/ 

import java.util.*;
import java.lang.*;
import java.io.*;
class Queue
{
	private int a[];
	private int front,rear;
	public Queue(int size)
	{
		a=new int[size];
		front =rear =-1;
		
	}


	
	public void push(int p)
  {
    if ((front == 0 && rear == a.length - 1)||(front == rear + 1))
    {
      System.out.println("OVERFLOW");
    } 
    else
    {
      if (front == -1)
        front = 0; //pushing elements in stack
      rear = (rear + 1) % a.length;
      a[rear] = p;
      System.out.println("PUSHED " + p);
    }
  }
	
	
	
	public int pop() 
  {
    int p;
    if (front == -1)
    {
      return -9999;
    } 
    else 
    {
      p = a[front];
      if (front == rear) 
      {
        front = -1;
        rear = -1;
      } 
      else 
      {
        front = (front + 1) % a.length; //popping elements from stack
      }
      return p;
    }
  }

	
	
		public int peek() 
  {
    int p;
    if (front == -1)
    {
      
      return -9999;
    } 
    else 
    {
     
      
      return a[front];
    }
    
    
  }


public static void main(String ar[])throws Exception
{
	DataInputStream z=new DataInputStream(System.in);
	
	Queue s1=new Queue(5);
	int ch,w;
	
	do
	{
		System.out.println("1.Push \n2.Pop \n3.Peek \n4.Exit");
		ch=Integer.parseInt(z.readLine()); //inputting users choice for push, pop, pee,k or exit
		
		switch(ch)
		{
			case 1:
	
	System.out.println("Enter element to be pushed");
				w=Integer.parseInt(z.readLine()); //inputting element to be pushed
				s1.push(w);
				break;
				
				case 2:
					w=s1.pop();
					if(w==-9999)
					System.out.println("UNDERFLOW");
					else
					System.out.println("Poped Value is:  "+w);
					break;
					
					case 3:
						w=s1.peek();
						if(w==-9999)
					System.out.println("UNDERFLOW");
					else
					System.out.println("Peeked Value is:  "+w);
					break;
			case 4:
				break;
				default:
				System.out.println("Invalid Choice");
			
			
			
			
			
		}	
			
		}while(ch!=4);
		
	}
}




1.Push
2.Pop
3.Peek
4.Exit
1
Enter element to be pushed
12
PUSHED 12
1.Push
2.Pop
3.Peek
4.Exit
1
Enter element to be pushed
13
PUSHED 13
1.Push
2.Pop
3.Peek
4.Exit
1
Enter element to be pushed
14
PUSHED 14
1.Push
2.Pop
3.Peek
4.Exit
1
Enter element to be pushed
15
PUSHED 15
1.Push
2.Pop
3.Peek
4.Exit
1
Enter element to be pushed
16
PUSHED 16
1.Push
2.Pop
3.Peek
4.Exit
1
Enter element to be pushed
17
OVERFLOW
1.Push
2.Pop
3.Peek
4.Exit
2
Poped Value is:  12
1.Push
2.Pop
3.Peek
4.Exit
2
Poped Value is:  13
1.Push
2.Pop
3.Peek
4.Exit
2
Poped Value is:  14
1.Push
2.Pop
3.Peek
4.Exit
2
Poped Value is:  15
1.Push
2.Pop
3.Peek
4.Exit
2
Poped Value is:  16
1.Push
2.Pop
3.Peek
4.Exit
2
UNDERFLOW
1.Push
2.Pop
3.Peek
4.Exit
3
UNDERFLOW
1.Push
2.Pop
3.Peek
4.Exit
4 
/*PROGRAM TO FIND THE POSTFIX OF THE GIVEN STRING */

import java.util.*;
class postfix
{
public static void main(String ab[])
{
Scanner sc=new Scanner(System.in);
int x,y,z=0;
String s,s1="";
char c;
System.out.println("Enter a string"); //inputting string
s=sc.nextLine();
char arr[]=new char[s.length()];
for(x=0;x<s.length();x++)
{
c=s.charAt(x);
if('a'<=c && c<='z')
s1=s1+c;
else
{
if(c=='-' || c=='+')
{
for(y=arr.length-1;y>=0;y--)
{
if(arr[y]=='(')
break;
if(arr[y]!='\u0000')
s1=s1+arr[y];
arr[y]='\u0000';
}
}
else
if(c=='*' || c=='/')
{
for(y=arr.length-1;y>=0;y--)
{
if(arr[y]=='(')
break;
if(arr[y]!='\u0000')
{
s1=s1+arr[y];
arr[y]='\u0000';
}
}
}
else
if(c=='^')
{
for(y=arr.length-1;y>=0;y--)
{
if(arr[y]=='(')
break;
if(arr[y]!='\u0000')
{
s1=s1+arr[y];
arr[y]='\u0000';
}
}
}
else
if(c==')')
{
for(y=arr.length-1;y>=0;y--)
{
if(arr[y]=='(')
{
arr[y]='\u0000';
break;
}
if(arr[y]!='\u0000')
s1=s1+arr[y];
arr[y]='\u0000';
}
}
for(y=0;y<arr.length-1;y++)
{
if(arr[y]=='\u0000')
{
for(z=y+1;z<arr.length-1;z++)
{
if(arr[z]!='\u0000')
{
arr[y]=arr[z];
arr[z]='\u0000';
break;
}
}
}
}
if(c!=')')
{
for(y=0;y<arr.length;y++)
{
if(arr[y]=='\u0000')
{
arr[y]=c;
break;
}
}
}
}
if(x==s.length()-1)
{
for(y=arr.length-1;y>=0;y--)
{
if(arr[y]!='\u0000')
s1=s1+arr[y];
}
}
}
System.out.println("Postfix Expression= "+s1); // printing the postfix expression
}
}



 
Enter a string
a/b+c*d-e^f+g/h
Postfix Expression= ab/cd*+e-f^-gh/+




























/*PROGRAM TO FIND THE LUCKY NUMBER*/

import java.util.*;
class luckynumber
{
public static void main(String kv[])
{
Scanner sc=new Scanner(System.in);
int i,y=0,j,b=0,k=0,p=0,n;
System.out.println("enter value of n"); // inputting value of n
n=sc.nextInt();
int a[]=new int[n];
System.out.println("fill the array");
for(i=0;i<n;i++)
a[i]=sc.nextInt();
for(;;)
{
if(k>0)		 
{			
k=Math.abs(k);	
while(b<k)	
{		
if(y<n)		
{		
if(a[y]!=0)		
{		
b=b+1;		
if(b!=k)		
y=y+1;		
}		
else		
y=y+1;		
}		
else		
y=0;		
}		
}		
else
{
k=Math.abs(k);	//0
while(b<k)	
{		
if(y>-1)		
{		
if(a[y]!=0)		
{		
b=b+1;		
if(b!=k)		
y=y-1;		
}		
else		
y=y-1;		
}		
else		
y=n-1;		
}		
}
k=a[y];
a[y]=0;
j=0;
b=0;
for(i=0;i<n;i++)
{
if(a[i]!=0)
{
p=i;
j=j+1;
}
}
if(j==1)
break;
}
for(i=0;i<n;i++)
System.out.println(a[i]);
System.out.println("lucky no. is= "+a[p]); //printing the lucky number
}
}
 
enter value of n
4
fill the array
5
4
9
14
0
4
0
0
lucky no. is= 4 
/*PROGRAM BASED ON CIRCULAR QUEUE*/

import java.util.*;
import java.io.*;
class circularqueue
{
    private int a[];
    private int f,r;
    public circularqueue(int size)
    {
        a=new int[size];
        f=-1;
        r=-1;
    }
    public void push(int p)
    {
        int k=0;
        if(f==0&&r==a.length-1||f==r+1)
        {
            //int k=0;
            k++;
            System.out.println("overflow");
        }
        else
        {
            if(f==-1)
            f=0;
            if(k==1)
            r=0;
            else
            r++;
            if(f>=0&&r==a.length)
            r=0;
            a[r]=p;
            System.out.println("pushed value= "+p); //printing the value pushed
        }
    }
    public int pop()
    {
        if(f==-1)
        return -9999;
        else
        {
            int b=a[f];
            f++;
            if(f>a.length-1)
            f=0;
            if(r==-1)
            f=-1;
            if(f==r)
            {
           // f=-1;
            r=-1;
        }
            return b;
        }
    }
    public int peek()
    {
        if(f==-1)
        return -9999;
        else
        {
            return a[f];
        }
    }

    public static void main(String kv[])
    {
        Scanner sc=new Scanner(System.in);
        DataInputStream z=new DataInputStream(System.in);
        int i,j,k,l,ch;
        System.out.println("enter size of array"); // inputting the size of array 
        l=sc.nextInt();
        circularqueue cq=new circularqueue(l);
        //int i,j,k,l,ch;
        do
        {
        System.out.println("1-push \n 2-pop \n 3-peek \n 4-exit");  //inputting the operation to be performed
        ch=sc.nextInt();
        switch(ch)
        {
            case 1:
            System.out.println("enter value to be pushed"); // inputting element to be pushed
            i=sc.nextInt();
            cq.push(i);
            break;
            case 2:
            System.out.println("popped value= "+cq.pop()); // printing the popped value
            break;
            case 3:
            System.out.println("peeked value= "+cq.peek()); //printing the peeked value
            break;
            case 4:
            break;
            default:
            System.out.println("enter a proper case");
        }
    }
    while(ch!=4);
}
}






 
enter size of array
5
1-push
 2-pop
 3-peek
 4-exit
1
enter value to be pushed
4
pushed value= 4
1-push
 2-pop
 3-peek
 4-exit
1
enter value to be pushed
3
pushed value= 3
1-push
 2-pop
 3-peek
 4-exit
1
enter value to be pushed
8
pushed value= 8
1-push
 2-pop
 3-peek
 4-exit
1
enter value to be pushed
5
pushed value= 5
1-push
 2-pop
 3-peek
 4-exit
1
enter value to be pushed
1
pushed value= 1
1-push
 2-pop
 3-peek
 4-exit
1
enter value to be pushed
22
overflow
1-push
 2-pop
 3-peek
 4-exit
2
popped value= 4
1-push
 2-pop
 3-peek
 4-exit
1
enter value to be pushed
22
pushed value= 22
1-push
 2-pop
 3-peek
 4-exit
3
peeked value= 3
1-push
 2-pop
 3-peek
 4-exit
1
enter value to be pushed
33
overflow
1-push
 2-pop
 3-peek
 4-exit
2
popped value= 3
1-push
 2-pop
 3-peek
 4-exit
2
popped value= 8
1-push
 2-pop
 3-peek
 4-exit
2
popped value= 5
1-push
 2-pop
 3-peek
 4-exit
2
popped value= 1
1-push
 2-pop
 3-peek
 4-exit
2
popped value= 22
1-push
 2-pop
 3-peek
 4-exit
2
underflow
1-push
 2-pop
 3-peek
 4-exit
4
 
/*PROGRAM BASED ON CONVERSION*/

import java.util.*;
class numsys
{
public static int dectobin(int n)
{
String s="";
int r,v;
while(n!=0)
{
r=n%2;
n=n/2;
s=(Integer.toString(r))+s;
}
v=Integer.parseInt(s);
return v;
}
public static int dectooct(int n)
{
String s="";
int r,v;
while(n!=0)
{
r=n%8;
n=n/8;
s=(Integer.toString(r))+s;
}
v=Integer.parseInt(s);
return v;
}
public static String dectohex(int n)
{
String s="";
int r;
char c;
while(n!=0)
{
r=n%16;
n=n/16;
if(r<10)
s=(Integer.toString(r))+s;
else
{
r=r+55;
c=(char)r;
s=String.valueOf(c)+s;
}
}
return s;
}
public static int bintodec(int n)
{
int d=0,r,s=0;
int m=n;
while(m!=0)
{
r=m%10;
m=m/10;
}
while(n!=0)
{
r=n%10;
s=s+(r*(int)Math.pow(2,d));
d++;
n=n/10;
}
return s;
}
public static int octtodec(int n)
{
int d=0,r,s=0;
while(n!=0)
{
r=n%10;
s=s+(r*(int)Math.pow(8,d));
d++;
n=n/10;
}
return s;
}
public static int hextodec(String n)
{
StringBuffer sb=new StringBuffer(n);
String s1=sb.reverse().toString(); //hexadecimal to decimal
int d,s=0;
char c;
for(int i=0;i<s1.length();i++)
{
c=s1.charAt(i);
d=c;
if(d>64)
d=d-55;
else
d=c-'0';
s=s+(d*(int)Math.pow(16,i));
}
return s;
}
public static int octtobin(int n)
{
int s=octtodec(n);
int y=dectobin(s);
return y;
}
public static int hextobin(String n)
{
int s=hextodec(n);
int y=dectobin(s); //hexadecimal to binary

return y;
}
public static String bintohex(int n)
{
String s=Integer.toString(n),s1,s2="";
int d,r,f=1;
d=s.length()%4;
for(int i=0;i<(4-d);i++)
s="0"+s;
d=0;
char c;
for(int i=0;i<(s.length()/4);i++)
{
s1=s.substring(d,4*f);
r=bintodec(Integer.parseInt(s1));
if(r<10)
s2=s2+(Integer.toString(r));
else
{
r=r+55;
c=(char)r;
s2=s2+String.valueOf(c);
}
d=d+4;
f=f+1;
}
return s2;
}
public static String octtohex(int n)
{
String s="",s1,s2;
int r,d;
StringBuffer sb=new StringBuffer(Integer.toString(n));
n=Integer.parseInt(sb.reverse().toString());
while(n!=0)
{
r=n%10;
s1=Integer.toString(octtobin(r));
d=3-s1.length();
for(int i=0;i<d;i++)
s1="0"+s1;
s=s+s1;
n=n/10;
}
return bintohex(Integer.parseInt(s));
}
public static int bintooct(int n)
{
String s=Integer.toString(n),s1,s2="";
int d,r,f=1; // binary to octal
d=s.length()%3;
for(int i=0;i<(3-d);i++)
s="0"+s;
d=0;
char c;
for(int i=0;i<(s.length()/3);i++)
{
s1=s.substring(d,3*f);
r=bintodec(Integer.parseInt(s1));
s2=s2+(Integer.toString(r));
d=d+3;
f=f+1;
}
return Integer.parseInt(s2);
}
public static int hextooct(String n)
{
String s=n,s1,s2="";
int d;
char c;
for(int i=0;i<s.length();i++)
{
c=s.charAt(i);
s1=Integer.toString(hextobin(String.valueOf(c)));
d=4-s1.length();
for(int j=0;j<d;j++)
s1="0"+s1;
s2=s2+s1;
}
return bintooct(Integer.parseInt(s2));
}
public static int binadd(String n1,String n2)
{
String s="";
int c=0,a,b,d,u;
int l1=n1.length(),l2=n2.length();
if(l1<l2)
{
for(int i=0;i<l2-l1;i++)
n1="0"+n1;
}
else
{
for(int i=0;i<l1-l2;i++)
n2="0"+n2;
}
n1="0"+n1;
n2="0"+n2;
StringBuffer sb=new StringBuffer(n1);
StringBuffer sb1=new StringBuffer(n2);
n1=sb.reverse().toString();
n2=sb1.reverse().toString();
for(int i=0;i<n1.length();i++)
{
a=n1.charAt(i)-'0';
b=n2.charAt(i)-'0';
d=dectobin(a+b+c);
c=bintodec(d/10);
s=s+Integer.toString(d%10);
}
StringBuffer sb2=new StringBuffer(s);
return Integer.parseInt(sb2.reverse().toString());
}
public static int octadd(String n1,String n2)
{
String s="";
int c=0,a,b,d,u;
int l1=n1.length(),l2=n2.length();
if(l1<l2)
{
for(int i=0;i<l2-l1;i++)
n1="0"+n1;
}
else
{
for(int i=0;i<=l1-l2;i++)
n2="0"+n2;
}
n1="0"+n1;
n2="0"+n2;
StringBuffer sb=new StringBuffer(n1);
StringBuffer sb1=new StringBuffer(n2);
n1=sb.reverse().toString();
n2=sb1.reverse().toString();
for(int i=0;i<n1.length();i++)
{
a=n1.charAt(i)-'0';
b=n2.charAt(i)-'0';
d=dectooct(a+b+c);
c=octtodec(d/10);
s=s+Integer.toString(d%10);
}
StringBuffer sb2=new StringBuffer(s);
return Integer.parseInt(sb2.reverse().toString());
}
public static String hexadd(String n1,String n2)
{
int c=0,a,b,u,t;
String d,s="";
int l1=n1.length(),l2=n2.length();
if(l1<l2)
{
for(int i=0;i<l2-l1;i++)
n1="0"+n1;
}
else
{
for(int i=0;i<=l1-l2;i++)
n2="0"+n2;
}
n1="0"+n1;
n2="0"+n2;
StringBuffer sb=new StringBuffer(n1);
StringBuffer sb1=new StringBuffer(n2);
n1=sb.reverse().toString();
n2=sb1.reverse().toString();
for(int i=0;i<n1.length();i++)
{
a=n1.charAt(i)-'0';
b=n2.charAt(i)-'0';
if(a>9)
a=a-7;
if(b>9)
b=b-7;
d=dectohex(a+b+c);
d="0"+d;
c=hextodec(d.substring(0,d.length()-1));
s=s+(String.valueOf(d.charAt(d.length()-1)));
}
StringBuffer sb2=new StringBuffer(s);
return sb2.reverse().toString();
}
public static int binsub(String n1,String n2)
{
String s="";
int a,b,d,u;
int l1=n1.length(),l2=n2.length();
for(int i=0;i<=l1-l2;i++)
n2="0"+n2;
StringBuffer sb=new StringBuffer(n1);
StringBuffer sb1=new StringBuffer(n2);
n1=sb.reverse().toString();
n2=sb1.reverse().toString();
int p[]=new int[n1.length()];
int q[]=new int[n2.length()];
for(int i=0;i<n1.length();i++)
{
p[i]=n1.charAt(i)-'0';
q[i]=n2.charAt(i)-'0';
}
for(int i=0;i<l1;i++)
{
u=i;
while(p[u]<q[u])
{
p[u]=p[u]+1;
u++;
}
if(u>i)
{
p[i]++;
p[u]--;
}
d=p[i]-q[i];
s=s+Integer.toString(d);
}
StringBuffer sb2=new StringBuffer(s);
return Integer.parseInt(sb2.reverse().toString());
}
public static int octsub(String n1,String n2)
{
String s="";
int a,b,d,u;
int l1=n1.length(),l2=n2.length();
for(int i=0;i<=l1-l2;i++)
n2="0"+n2;
StringBuffer sb=new StringBuffer(n1);
StringBuffer sb1=new StringBuffer(n2);
n1=sb.reverse().toString();
n2=sb1.reverse().toString();
int p[]=new int[n1.length()];
int q[]=new int[n2.length()];
for(int i=0;i<n1.length();i++)
{
p[i]=n1.charAt(i)-'0';
q[i]=n2.charAt(i)-'0';
}
for(int i=0;i<l1;i++)
{
u=i;
while(p[u]<q[u])
{
p[u]=p[u]+7;
u++;
}
if(u>i)
{
p[i]++;
p[u]--;
}
d=p[i]-q[i];
s=s+Integer.toString(d);
}
StringBuffer sb2=new StringBuffer(s);
return Integer.parseInt(sb2.reverse().toString());
}
public static String hexsub(String n1,String n2)
{
String s="";
int a,b,d,u;
int l1=n1.length(),l2=n2.length();
for(int i=0;i<=l1-l2;i++)
n2="0"+n2;
StringBuffer sb=new StringBuffer(n1);
StringBuffer sb1=new StringBuffer(n2);
n1=sb.reverse().toString();
n2=sb1.reverse().toString();
int p[]=new int[n1.length()];
int q[]=new int[n2.length()];
for(int i=0;i<n1.length();i++)
{
p[i]=hextodec(Character.toString(n1.charAt(i)));
q[i]=hextodec(Character.toString(n2.charAt(i)));
}
for(int i=0;i<l1;i++)
{
u=i;
while(p[u]<q[u])
{
p[u]=p[u]+15;
u++;
}
if(u>i)
{
p[i]++;
p[u]--;
}
d=p[i]-q[i];
s=s+dectohex(d);
}
StringBuffer sb2=new StringBuffer(s);
return sb2.reverse().toString();
}

public static void main(String at[])
{
Scanner sc=new Scanner(System.in);
int ch;
do{
System.out.println("Enter=>");
System.out.println("1 : Conversion");
System.out.println("2 : Addition");
System.out.println("3 : Multiplication");
System.out.println("4 : Subtraction");
System.out.println("5 : End the program");
 ch=sc.nextInt();
switch(ch)
{
case 1:
{
int ch1;
do{
System.out.println("Enter=>");
System.out.println("1 : Decimal to Binary");
System.out.println("2 : Decimal to Octal");
System.out.println("3 : Decimal to Hexadecimal");
System.out.println("4 : Binary to Decimal");
System.out.println("5 : Octal to decimal");
System.out.println("6 : Octal to Hexadecimal");
System.out.println("7 : Hexadecimal to Octal");
System.out.println("8 : Hexadecimal to Decimal");
System.out.println("9 : Go to main menu");
ch1=sc.nextInt();
switch(ch1)
{
case 1:
System.out.println("Enter a decimal number");
System.out.println("Answer = "+dectobin(sc.nextInt()));
break;
case 2:
System.out.println("Enter a decimal number");
System.out.println("Answer = "+dectooct(sc.nextInt()));
break;
case 3:
System.out.println("Enter a decimal number");
System.out.println("Answer = "+dectohex(sc.nextInt()));
break;
case 4:
System.out.println("Enter a binary number");
System.out.println("Answer = "+bintodec(sc.nextInt()));
break;
case 5:
System.out.println("Enter a octal number");
System.out.println("Answer = "+octtodec(sc.nextInt()));
break;
case 6:
System.out.println("Enter a octal number");
System.out.println("Answer = "+octtohex(sc.nextInt()));
break;
case 7:
System.out.println("Enter a hexadecimal number");
System.out.println("Answer = "+hextooct(sc.nextLine()));
break;
case 8:
System.out.println("Enter a hexadecimal number");
System.out.println("Answer = "+hextodec(sc.nextLine()));
break;
case 9:
break;
}}while(ch1!=9);
break;
}
case 2:
{
int ch1;
do{
System.out.println("Enter=>");
System.out.println("1 : Binary addition");
System.out.println("2 : Octal addition");
System.out.println("3 : Hexadecimal addition");
System.out.println("4 : Go to main menu");
ch1=sc.nextInt();
switch(ch1)
{
case 1://binary addition
{
System.out.println("Enter the Binary nos.");
String n1=sc.next();
String n2=sc.next();
System.out.println("Binary sum is = "+binadd(n1,n2));
break;
}
case 2://octal addition
{
System.out.println("Enter the octal nos.");
String n1=sc.next();
String n2=sc.next();
System.out.println("Octal sum is = "+octadd(n1,n2));
break;
}
case 3://hexadecimal addition
{
System.out.println("Enter the hexadecimal nos.");
String n1=sc.next();
String n2=sc.next();
System.out.println("Hexadecimal sum is = "+hexadd(n1,n2));
break;
}
case 4:
break;
}}while(ch1!=4);
break;
}
case 3://multiplication
{
 int ch1;
do{
System.out.println("Enter=>");
System.out.println("1 : Binary multiplication");
System.out.println("2 : Octal multiplication");
System.out.println("3 : Hexadecimal multiplication");
System.out.println("4 : Go to main menu");
ch1=sc.nextInt();
switch(ch1)
{
case 1://binary multiplication
{
System.out.println("Enter the binary nos.");
String n1=sc.next();
String n2=sc.next();
StringBuffer sb=new StringBuffer(n1);
StringBuffer sb1=new StringBuffer(n2);
n1=sb.reverse().toString();
n2=sb1.reverse().toString();
int a,b,d=0;
String p1,p2,s="";
for(int i=0;i<n2.length()/2;i++)
{
a=n2.charAt((int)d)-'0';
p1=Integer.toString(a*Integer.parseInt(n1));
StringBuffer sb2=new StringBuffer(p1);
p1=sb2.reverse().toString();
for(int j=0;j<d;j++)
p1=p1+"0";
d++;
b=n2.charAt(d)-'0';
p2=Integer.toString(b*Integer.parseInt(n1));
StringBuffer sb3=new StringBuffer(p2);
p2=sb3.reverse().toString();
for(int j=0;j<d;j++)
p2=p2+"0";
d++;
s=Integer.toString(binadd(s,Integer.toString(binadd(p1,p2))));
}
System.out.println("Binary Product is = "+s);
break;
}
case 2://octal multiplication
{
System.out.println("Enter the octal nos.");
String n1=sc.next();
String n2=sc.next();
n2="0"+n2;
n1="0"+n1;
StringBuffer sb=new StringBuffer(n1);
StringBuffer sb1=new StringBuffer(n2);
n1=sb.reverse().toString();
n2=sb1.reverse().toString();
int a,b,d=0,m,c=0;
String p1="",p2="",s="";
for(int i=0;i<n2.length()/2;i++)
{
a=n2.charAt((int)d)-'0';
for(int j=0;j<n1.length();j++)
{
m=dectooct((a*(int)(n1.charAt(j)-'0'))+c);
p1=p1+Integer.toString(m%10);
c=m/10;
}
c=0;
StringBuffer sb2=new StringBuffer(p1);
p1=sb2.reverse().toString();
for(int j=0;j<d;j++)
p1=p1+"0";
d++;
b=n2.charAt((int)d)-'0';
for(int j=0;j<n1.length();j++)
{
m=dectooct((b*(int)(n1.charAt(j)-'0'))+c);
p2=p2+Integer.toString(m%10);
c=m/10;
}
StringBuffer sb3=new StringBuffer(p2);
p2=sb3.reverse().toString();
for(int j=0;j<d;j++)
p2=p2+"0";
d++;
s=Integer.toString(octadd(s,Integer.toString(octadd(p1,p2))));
c=0;
p1="";
p2="";
}
System.out.println("Octal product is = "+s);
break;
}
case 3://hexadecimal multiplication
{
System.out.println("Enter the hexadecimal nos.");
String n1=sc.next();
String n2=sc.next();
n2="0"+n2;
n1="0"+n1;
StringBuffer sb=new StringBuffer(n1);
StringBuffer sb1=new StringBuffer(n2);
n1=sb.reverse().toString();
n2=sb1.reverse().toString();
int a,b,d=0,cl;
String p1="",p2="",s="0",m,c="";
for(int i=0;i<n2.length()/2;i++)
{
a=hextodec(Character.toString(n2.charAt(d)));
for(int j=0;j<n1.length();j++)
{
cl=hextodec(Character.toString(n1.charAt(j)));
m=dectohex((a*cl)+hextodec(c));
if(m.length()>0)
{
p1=p1+Character.toString(m.charAt(m.length()-1));
c=m.substring(0,m.length()-1);
}
else
{
c="0";
}
}
c="0";
StringBuffer sb2=new StringBuffer(p1);
p1=sb2.reverse().toString();
for(int j=0;j<d;j++)
p1=p1+"0";
d++;
b=hextodec(Character.toString(n2.charAt((int)d)));
for(int j=0;j<n1.length();j++)
{
cl=hextodec(Character.toString(n1.charAt(j)));
m=dectohex((b*cl)+hextodec(c));
if(m.length()>0)
{
p2=p2+Character.toString(m.charAt(m.length()-1));
c=m.substring(0,m.length()-1);
}
else
{
c="0";
}
}
c="0";
StringBuffer sb3=new StringBuffer(p2);
p2=sb3.reverse().toString();
for(int j=0;j<d;j++)
p2=p2+"0";
d++;
s=hexadd(s,hexadd(p1,p2));
p1="";
p2="";
}
System.out.println("Hexadecimal product is = "+s);
break;
}
case 4:
break;
}}while(ch1!=4);
break;
}
case 4://subtraction
int ch1;
do{
System.out.println("Enter=>");
System.out.println("1 : Binary subtraction");
System.out.println("2 : Octal subtraction");
System.out.println("3 : Hexadecimal subtraction");
System.out.println("4 : Go to main menu");
ch1=sc.nextInt();
switch(ch1)
{
case 1://binary subtraction
{
System.out.println("Enter the binary nos.");
String n1=sc.next();
String n2=sc.next();
if(Integer.parseInt(n2)>Integer.parseInt(n1))
System.out.println("Binary difference = -"+binsub(n2,n1));
else
System.out.println("Binary difference = "+binsub(n1,n2));
}
break;
case 2://octal multiplication
{
System.out.println("Enter the octal nos.");
String n1=sc.next();
String n2=sc.next();
if(Integer.parseInt(n2)>Integer.parseInt(n1))
System.out.println("Octal difference = -"+octsub(n2,n1));
else
System.out.println("Octal difference = "+octsub(n1,n2));
}
break;
case 3://hexadecimal multiplication
{
System.out.println("Enter the hexadecimal nos.");
String n1=sc.next();
String n2=sc.next();
if(n2.compareTo(n1)>0)
System.out.println("Hexadecimal difference = -"+hexsub(n2,n1));
else
System.out.println("Hexadecimal difference = "+hexsub(n1,n2));
}
break;
case 4:
break;
}}while(ch1!=4);
break;
case 5:
break;
}}while(ch!=5);
}
}
Enter=>
1 : Conversion
2 : Addition
3 : Multiplication
4 : Subtraction
5 : End the program
1
Enter=>
1 : Decimal to Binary
2 : Decimal to Octal
3 : Decimal to Hexadecimal
4 : Binary to Decimal
5 : Octal to decimal
6 : Octal to Hexadecimal
7 : Hexadecimal to Octal
8 : Hexadecimal to Decimal
9 : Go to main menu
1
Enter a decimal number
45
Answer = 101101
Enter=>
1 : Decimal to Binary
2 : Decimal to Octal
3 : Decimal to Hexadecimal
4 : Binary to Decimal
5 : Octal to decimal
6 : Octal to Hexadecimal
7 : Hexadecimal to Octal
8 : Hexadecimal to Decimal
9 : Go to main menu
2
Enter a decimal number
12
Answer = 14
Enter=>
1 : Decimal to Binary
2 : Decimal to Octal
3 : Decimal to Hexadecimal
4 : Binary to Decimal
5 : Octal to decimal
6 : Octal to Hexadecimal
7 : Hexadecimal to Octal
8 : Hexadecimal to Decimal
9 : Go to main menu
3
Enter a decimal number
12
Answer = C
Enter=>
1 : Decimal to Binary
2 : Decimal to Octal
3 : Decimal to Hexadecimal
4 : Binary to Decimal
5 : Octal to decimal
6 : Octal to Hexadecimal
7 : Hexadecimal to Octal
8 : Hexadecimal to Decimal
9 : Go to main menu
4
Enter a binary number
110101
Answer = 53
Enter=>
1 : Decimal to Binary
2 : Decimal to Octal
3 : Decimal to Hexadecimal
4 : Binary to Decimal
5 : Octal to decimal
6 : Octal to Hexadecimal
7 : Hexadecimal to Octal
8 : Hexadecimal to Decimal
9 : Go to main menu
5
Enter a octal number
456
Answer = 302
Enter=>
1 : Decimal to Binary
2 : Decimal to Octal
3 : Decimal to Hexadecimal
4 : Binary to Decimal
5 : Octal to decimal
6 : Octal to Hexadecimal
7 : Hexadecimal to Octal
8 : Hexadecimal to Decimal
9 : Go to main menu
6
Enter a octal number
456
Answer = 12E
Enter=>
1 : Decimal to Binary
2 : Decimal to Octal
3 : Decimal to Hexadecimal
4 : Binary to Decimal
5 : Octal to decimal
6 : Octal to Hexadecimal
7 : Hexadecimal to Octal
8 : Hexadecimal to Decimal
9 : Go to main menu
 
/*PROGRAM TO ENCODE AND DECODE*/
import java.util.*;
class EncodeDecode
{
public static void main(String ar[])
{
Scanner z=new Scanner(System.in);
System.out.println("Enter Choice\n 1Encode \n 2Decode");                             //giving option
int ch=z.nextInt();
EncodeDecode sd=new EncodeDecode();
if(ch==1)
sd.encode();
else if(ch==2)
sd.decode();
else
System.out.println("Not a Valid Choice");
String s=z.nextLine();
}
public void encode()
{Scanner sc=new Scanner(System.in);
System.out.println("Enter String in Upper Case");
String s=sc.nextLine();
StringTokenizer st=new StringTokenizer(s);
int a=st.countTokens(),x=0;
String ar[]=new String[a];
for(x=0;x<a;x++)
ar[x]=st.nextToken();
int k=a,l=0,asc=0;
String j="",u="",fs="";
char ch='\u0000';
while(k>0)
{
k--;
j=ar[k];
l=j.length();
u=u+((char)(64+l));
for(x=0;x<l;x++)
{
ch=j.charAt(x);
asc=ch;
if((asc+l)<91)
ch=(char)(asc+l);
else
{
asc=(asc+l)-26;
ch=(char)asc;
}
u=u+ch;
}
fs=u+fs;
u="";
}
System.out.println("Output="+fs);
}
public void decode()
{
Scanner sx=new Scanner(System.in);
System.out.println("Enter String in Upper Case to decode");
String s=sx.nextLine();
int chi=0,x=1,asc=0;
String dec="",temp="";
char chl='\u0000',ab='\u0000';
while (s.length()>1)
{
chl=s.charAt(0);
chi=(int)chl;
chi=chi-64;
for(x=1;x<=chi;x++)asc=s.charAt(x);
if ((asc-chi)>=65)
{
ab=(char)(asc-chi);
}
else
{
asc=(asc-chi)+26;
ab=(char)asc;
}
temp=temp+ab;ab=' ';
}
dec=dec+" "+temp;
temp="";
StringBuffer sb=new StringBuffer(s);
sb.delete(0,(chi+1));
chi=0;
s=sb.toString();
}
System.out.println("Decoded String-"+dec);                                   //result
}
} 
Enter Choice
 1Encode 
2Decode 
1
Enter String in Upper Case 
YOU ARE HERE
Output= LBH NER URER
 

/*PROGRAM TO CALCULATE TIME DIFFERENCE*/
import java.util.*;
class Time
{
  public static void main(String at[])
  {
    Scanner sc=new Scanner(System.in);  //creating an object of the scanner class
    System.out.print("Enter first time  = ");
    String a=sc.nextLine();   //inputting the first time
    System.out.print("Enter second time = ");
    String b=sc.nextLine();   //inputting the second time
    String k1[]=a.split(":");
    String k2[]=b.split(":");
    int sec1=Integer.parseInt(k1[0])*3600+Integer.parseInt(k1[1])*60+Integer.parseInt(k1[2]); //converting the 1st time into seconds
    int sec2=Integer.parseInt(k2[0])*3600+Integer.parseInt(k2[1])*60+Integer.parseInt(k2[2]); //converting the 2nd time into seconds
    int sec;
    if(sec2>sec1)  //checking if the 2nd time is greater or not
      sec=sec2-sec1;  //calculating the time diff in seconds
    else
      sec=3600*24+sec2-sec1;
    int hrs,min,sec3;
    hrs=sec/3600;
    min=(sec%3600)/60;
    sec3=sec%60;
    System.out.println();
    System.out.print("Total time difference = ");  //from here the printing the time difference takes place
    if((hrs+"").length()!=2)
      System.out.print("0"+hrs+":");
    else
      System.out.print(hrs+":");
    if((min+"").length()!=2)
      System.out.print("0"+min+":");
    else
      System.out.print(min+":");
    if((sec3+"").length()!=2)
      System.out.print("0"+sec3);
    else
      System.out.print(sec3);
  }
}

	
 
Enter first time  = 06:27:43
Enter second time = 09:13:57

Total time difference = 02:46:14
 
/* PROGRAM SHOWING  FILE HANDLING */
import java.io.*;
class filehandling
{
public static void main(String ar[])throws Exception
{
DataInputStream z=new DataInputStream(System.in);
String n,m;
String k[];
int r;
double m1;
FileWriter f1;
PrintWriter p1;
FileReader f2;
BufferedReader b1;
File f;
ab:while(true)
{
f1=new FileWriter("temp.dat");
p1=new PrintWriter(f1);
f2=new FileReader("xyz.dat");
b1=new BufferedReader(f2);
System.out.println("Enter choice \n1. To change Name\n2. To change Computer marks\n3. To change English marks\n4. Exit");
switch(Integer.parseInt(z.readLine()))
{
case 1:
System.out.println("Enter Roll no. & New name");
r=Integer.parseInt(z.readLine());
n=z.readLine();
while((m=b1.readLine())!=null)
{
k=m.split("@");
if(Integer.parseInt(k[0])==r)
p1.println(k[0]+"@"+n+"@"+k[2]+"@"+k[3]);
else
p1.println(m);
}
b1.close();
f2.close();
p1.close();
f1.close();
f=new File("xyz.dat");
f.delete();
f=new File("temp.dat");
f.renameTo(new File("xyz.dat")); 
break;
case 2:
System.out.println("Enter Choice\n1.Particular Student\n2.All Students");
switch(Integer.parseInt(z.readLine()))
{
case 1:
System.out.println("Enter Roll number and new marks in Computer");
r=Integer.parseInt(z.readLine());
m1=Double.parseDouble(z.readLine());
while((m=b1.readLine())!=null)
{
k=m.split("@");
if(Integer.parseInt(k[0])==r)
p1.println(k[0]+"@"+k[1]+"@"+m1+"@"+k[3]);
else
p1.println(m);
}
b1.close();
f2.close();
p1.close();
f1.close();
f=new File("xyz.dat");
f.delete();
f=new File("temp.dat");
f.renameTo(new File("xyz.dat")); 
break;
case 2:
System.out.println("Enter new marks in Computer");
while((m=b1.readLine())!=null)
{
m1=Double.parseDouble(z.readLine());
k=m.split("@");
p1.println(k[0]+"@"+k[1]+"@"+m1+"@"+k[3]);
}
b1.close();
f2.close();
p1.close();
f1.close();
f=new File("xyz.dat");
f.delete();
f=new File("temp.dat");
f.renameTo(new File("xyz.dat")); 
break;
default:
System.out.println("Wrong Input");
}
break;
case 3:
System.out.println("Enter Choice\n1.Particular Student\n2.All Students");
switch(Integer.parseInt(z.readLine()))
{
case 1:
System.out.println("Enter Roll Number & new marks in English");
r=Integer.parseInt(z.readLine());
m1=Double.parseDouble(z.readLine());
while((m=b1.readLine())!=null)
{
k=m.split("@");
if(Integer.parseInt(k[0])==r)
p1.println(k[0]+"@"+k[1]+"@"+k[2]+"@"+m1);
else
p1.println(m);
}
b1.close();
f2.close();
p1.close();
f1.close();
f=new File("xyz.dat");
f.delete();
f=new File("temp.dat");
f.renameTo(new File("xyz.dat")); 
break;
case 2:
System.out.println("Enter new marks in English");
while((m=b1.readLine())!=null)
{
m1=Double.parseDouble(z.readLine());
k=m.split("@");
p1.println(k[0]+"@"+k[1]+"@"+k[2]+"@"+m1);
}
b1.close();
f2.close();
p1.close();
f1.close();
f=new File("xyz.dat");
f.delete();
f=new File("temp.dat");
f.renameTo(new File("xyz.dat")); 
break;
default:
System.out.println("Wrong Option");
}
break;
case 4:
break ab;
default:
System.out.println("Wrong Option");
}
}
} }
type xyz.txt
1@rmn@23.0@32.0
2@def@43.0@45.0
3@fgh@56.0@65.0
4@rts@78.0@89.0
5@xyz@99.0@100.0

 java filehandling
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
1
Enter Roll no. & New name
2
erfg
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
2
Enter Choice
1.Particular Student
2.All Students
1
Enter Roll number and new marks in Computer
1
88.0
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
2
Enter Choice
1.Particular Student
2.All Students
2
Enter new marks in Computer
11.0
12.0
13.0
14.0
15.0
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
3
Enter Choice
1.Particular Student
2.All Students
1
Enter Roll Number & new marks in English
3
67.0
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
3
Enter Choice
1.Particular Student
2.All Students
2
Enter new marks in English
17.0
18.0
19.0
20.0
21.0
Enter choice
1. To change Name
2. To change Computer marks
3. To change English marks
4. Exit
4

type xyz.txt
1@rmn@11.0@17.0
2@erfg@12.0@18.0
3@fgh@13.0@19.0
4@rts@14.0@20.0















/* PROGRAM TO SHOW STACK METHOD*/
import java.util.*;
import java.io.*;
class Stack
 {
  private int a[],tos;
  public Stack(int size)
   {
    a=new int[size];
    tos=-1;
   }//end of Stack constructor
  public void push(int p)
   {
    if(tos==a.length-1)
    System.out.println("Overflow");
    else
     {
      a[++tos]=p;
     }
   }//end of push
  public int pop()
   {
    if(tos==-1)
    return -9999;
    else
    {
     return a[tos--];
    }
   }//end of pop
  public int peek()
  {
   if(tos==-1)
   return -9999;
   else
   return a[tos];
  }
}//end of class Stack

  class q3_stack
   {
    public static void main(String at[])
    {
     Scanner sc=new Scanner(System.in);
     int l,ch,p;
     System.out.println("Enter length of stack array");
     l=sc.nextInt();
     Stack s1=new Stack(l);
     do
      {
       System.out.println("1-Push\n2-Pop\n3-Peek\n4-Exit");
       ch=sc.nextInt();
       switch(ch)
       {
         case 1:
         System.out.println("Enter element to be pushed");
         p=sc.nextInt();
         s1.push(p);
         break;
         case 2:
         p=s1.pop(); 
         if(p==-9999)
         System.out.println("Underflow");
         else
         System.out.println("Poped value="+p);
         break;
         case 3:
         p=s1.peek();
         if(p==-9999)
         System.out.println("Underflow");
         else
         System.out.println("Peeked value="+p);
         break;
         case 4:
         break;
         default:
         System.out.println("Wrong option");
         break;
       }//end of switch
      }//end of do while loop
      while(ch!=4);
    }//end of main
   }//end of class q3_stack 
Enter length of stack array
5
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
1
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
2
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
3
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
4
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
5
1-Push
2-Pop
3-Peek
4-Exit
1
Enter element to be pushed
6
Overflow
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=5
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=4
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=3
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=2
1-Push
2-Pop
3-Peek
4-Exit
2
Poped value=1
1-Push
2-Pop
3-Peek
4-Exit
4
 
 

