# square-root-of-a-number-using-binary-search


#include<bits/stdc++.h>

using namespace std;

int squareroot(long long int number) {
    
    long long int mid=number/2, ans;
    
    long long int start=1, end=number;
    
    
    while(start<=end)  {
        
        if((mid*mid)==number)   return mid;
        
        else if((mid*mid)<number) {
            
           
            start=mid+1;
            ans=mid;
        }
        
        else    {
            
            end=mid-1;
        }
         mid=start+(end-start)/2;
    }
    return ans;
} 

long double moreprecission(long long int sq,int precission,long long int number)  {
    
    
    long double factor=1;
    long double ans=sq;
    for(int i=1;i<=precission;i++)  {
        
        factor=factor/10;
        
        for(long double j=ans;j*j<number;j=j+factor)  {
            
         ans=j;   
            
        }
    }
    
    return ans;
    
}

int main() {
    
    long long int number;
    int precission;
    cin>>number>>precission;
    
    long long int sq=squareroot(number);
    
    cout<<moreprecission(sq,precission,number)<<'\n';
    
}
