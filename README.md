# Binary-

#include <stdio.h>

int binary_search_recursive(int arr[],int target,int lo,int hi)
{
    if(lo>hi) return -1;
    int mid=(lo+hi)/2;
    if(arr[mid]==target) return mid;
    if(arr[mid]<target)
    {
        return binary_search_recursive(arr ,target,mid+1,hi);
    }
    else
    {
        return binary_search_recursive(arr ,target,lo,mid-1);
    }
}
int main() {
    int n,target;
    printf("Enter limit : ");
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++)
    {
        printf("Enter %d element : ",i+1);
       scanf("%d",&arr[i]);
    }
    printf("Enter target : ");
    scanf("%d",&target);
    printf("Index of target element  = %d",binary_search_recursive(arr,target,0,n-1));
    return 0;
}
