# q3-
A palindromic number reads the same both ways. The smallest 6 digit palindrome made from the product of two 3-digit numbers is 101101=143 X 707 .
Find the largest palindrome made from the product of two 3-digit numbers which is less than N .  
Input Format  
First line contains T that denotes the number of test cases. This is followed by T lines, each containing an integer, N. 
Constraints 
1<=T<=100
101101<=N<=1000000
Output Format  
Print the required answer for each test case in a new line. 
Sample Input 0 
2
101110
800000 
Sample Output 0 
101101 
793397
Explanation 0  
101101 is product of 143 and 707 .
793397 is product of 869 and 913 

#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int palindrome(long int v)
{
   
 long int reverse,n,i,j;
    n=v;
    while (n != 0)
   {
      reverse = reverse * 10;
      reverse = reverse + n%10;
      n       = n/10;
   }
    if(reverse==v)
    {
     for(i=100;i<=999;i++)
         {
         for(j=100;j<=999;j++)
          {
           if(i*j==v)
               return 1;

         }
     }
        return 0;
    }
    else
        {
        return 0;
    }
}
int main() {

    int t;
    scanf("%d",&t);
    while(t--)
        {
        long int val;
        scanf("%ld",&val);
        int f=0;
        while(f==0)
            {
            f=palindrome(--val);
        }
        printf("%ld\n",val);
    }
    return 0;
}
