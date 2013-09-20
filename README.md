#include <iostream>
using namespace std;
 void quick_sort(int []s,int low,int high)
 {
    if(low<high)
    {
      int i=low;j=high;x=s[low];
      while(i<j)
      {
        while(i<j && s[j]>=x)
          j--;
        if(i<j)
          s[i++]=s[j];
        while(i<j && s[i]<x)
          i++;
        if(i<j)
          s[j--]=s[i];
      }
      s[i]=x;
      quick_sort(s,low,i-1);
      quick_sort(s,i+1,high);
    }
 }
 
 int main()
 {
    int s[]={1,9,2,8,3,4,7,6,0,6,11};
    quick_sort(s,0,10);
    for(int i=0;i<11;i++)
    {
      printf("%d\t",s[i]);
    }
 }
