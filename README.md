# Code-I-wrote-as-an-undergraduate
For 100,000 lines of code
#include<iostream>
using namespace std;
void sort(int a[],int l,int r,int n);
int main()
{
    int a[1000];
    int n,l,r;
    cin>>n>>l>>r;
    for(int i=0;i<n;++i)
    {
        cin>>a[i];
    }
    sort(a,l,r,n);
    return 0;
}

void sort(int a[],int l,int r,int n)
{
  for(int i=0;i<n-1;++i)        //外循环还是从全局出发，在不确定l,r的具体大小时//
  {
      if(i>=l&&i<=r)        
      {
          int min=i;
          for(int j=i;j<=r;++j)     //这里的小细节注意一下，内循环的遍历应从所给的变量r上限值为循环终点，而不是数组的原始长度n-1//
          {
              if(a[min]>a[j])
              {
                  min=j;
              }
          }
          int t=a[min];
          a[min]=a[i];
          a[i]=t;
      }
  }

      for(int i=0;i<n;++i)
      {
          cout<<a[i]<<' ';
      }
}
