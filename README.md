# Code_help,/*Q. Given an unsorted array with both positive and negative elements. Find the smallest
positive number missing from the array in O(n) time using constant extra space. It is
allowed to modify the original array.*/
#include<iostream>
using namespace std;

int isContain(int n,int l,int arr[])
{
int i,f=0;
for(i=0;i<l;i++)
{
    if(n==arr[i])
    f++;

}
if(f==0)
    return 0;
else
    return 1;
}
int main()
{
     int i,j,n,minIndex=0,temp=0;
     cout<<"Enter Size of Array: ";
     cin>>n;
     int arr[n];
      cout<<"Enter Array Elements: ";
     for(i=0;i<n;i++)
        cin>>arr[i];

    
      for(j=i;j<n;j++)
         {
         if(minIndex<n)
         {
             if(arr[j]<arr[minIndex])
            { minIndex=j;
             temp=arr[i];
             arr[i]=arr[minIndex];
             arr[minIndex]=temp;
             
            }
            minIndex++;
         }
         }
     
int f=0;

   if(arr[n-1]>0)
   {

   for(i=1;i<=arr[n-1];i++)
   {



         if(isContain(i,n,arr)==0)
         {
             cout<<i<<" ";
             f=1;
             break;


      }

   }
   if(f==0)
     cout<<arr[n-1]+1;

   }
   if(arr[n-1]<0)
    cout<<"1";



    return 0;
}
