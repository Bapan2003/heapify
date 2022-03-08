// Online C compiler to run C program online
#include <stdio.h>
void buildHeap(int a[],int n,int i);
int main() {
    // Write C code here
    int n;
    printf("Enter the length of array\n");
    scanf("%d",&n);
    int a[n];
    printf("Enter the element of array respectively");
    for(int i=1;i<=n;i++){
       scanf("&d",&a[i]);  
    }
    for(int i=n/2;i>=1;i--){
        buildHeap(a,n,i);
    }
    for(int i=1;i<=n;i++){
        printf("%d",a[i]);
    }
    
    return 0;
}
void buildHeap(int a[],int n,int i){
    int largest =i;
    int l= 2i;
    int r = 2i+1;
    if(l<=n&& a[l]>a[largest])
      largest =l;
    if(r<=n && a[r]>a[largest])
      largest=r;
    if(largest !=i){
        int temp = a[i];
        a[i] = a[largest];
        a[largest] =temp;
        buildHeap(a,n,largest);
    }
    //buildHeap(a,n,largest);
}
