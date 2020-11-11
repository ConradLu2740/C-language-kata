# C-language-kata
PROBLEM :
Task
Given a list of digits, return the smallest number that could be formed from these digits, using the digits only once (ignore duplicates).

Notes:
Only positive integers will be passed to the function (> 0 ), no negatives or zeros.
Input >> Output Examples
minValue ({1, 3, 1})  ==> return (13)
Explanation:
(13) is the minimum number could be formed from {1, 3, 1} , Without duplications

minValue({5, 7, 5, 9, 7})  ==> return (579)
Explanation:
(579) is the minimum number could be formed from {5, 7, 5, 9, 7} , Without duplications

minValue({1, 9, 3, 1, 7, 4, 6, 6, 7}) return  ==> (134679)
Explanation:
(134679) is the minimum number could be formed from {1, 9, 3, 1, 7, 4, 6, 6, 7} , Without duplications


MY SOLUTION:
#include <stdlib.h>
#include <math.h> 

int minValue(const int* values, const size_t len)
{int i,h,m=-1;
 int sum=0;
 int valuesn[len];
 int flag=0;
 for(i=0;i<len;i++)
   {
    for(h=0;h<=i;h++)
     {if((values[h]!=values[i]))
       flag++;
     }
      if(flag==i)valuesn[m++]=values[i];
   }//select
 
 int n;
 for(i=0;i<m;i++)
   {
   for(n=i+1;n<m;n++)
     {
     if(valuesn[i]>valuesn[n])valuesn[i]=valuesn[n];
     }
  }
 
 for(i=0;i<m;i++)
     {
     sum=sum+(valuesn[i])*pow(10,m-i);
   }
 return sum;
  return 1;
}
