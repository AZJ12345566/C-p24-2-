# C-p24-2-
C语言学习笔记 p24作业详解(2)
#include<stdio.h>
#include<string.h>
int count_bit_one(int n)//这里用int如果输入负数可能影响输出结果，可以改成unsigned int
{
    while(n)
    {
        if(n%2==1)
        {
            count++;
        }
        n=n/2;
    }
    return count;
}
//解法2
int count_bit_one(int n)
{
    int count=0;
    int i=0;
    for(i=0;i<32;i++)
    {
        if(((n>>i)&1)==1)
        {
            count++;
        }
    }
}
//解法3
int count_bit_one(int n)
{
    int count=0;
    while(n)
    {
        n=n&(n-1);
        count++;
    }
    return count
}
int main()
{
    int a=0;
    scanf("%d",,&a);
    //写一个函数求a的二进制(补码)表示中有几个1
    int count_bit_one(a);
    printf("count=%d\n",count);
    return 0;
}



//找出两个数二进制位相异的二进制位个数
int get_diff_bit(int m,int n)
{
    int tmp=m^n;
    int count=0;
    //return count_bit_one(tmp);
    while(tmp)
    {
        tmp=tmp&(tmp-1);
        count++;
    }
    return count;
}
int main()
{
    int m=0;
    int n=0;
    scanf("%d%d",&m,&n);
    int count=get_diff_bit(m.n);
    printf("count=%d\n",count);
    return 0;
}

void print(int m)
{
    int i=0;
    printf("奇数位:\n");
    for(i=31;i>=1;i-=2)
    {
        printf("%d",(m>>i)&1);
    }
    printf("\n");
}
int main()
{
    int m=0;
    scanf("%d",&m);
    print(m);
    return 0;
}

//用指针打印数组内容
print(int* p,int sz)
{
    int i=0;
    for(i=0;i<sz;i++)
    {
        printf("%d",*(p+i);
    }
}
int main()
{
    int arr[]={1,2,3,4,5,6,7,8,9};
    int sz=sizeof(arr)/sizeof(arr[0]);
    print(arr,sz);
    return 0;
}

//九九乘法表
void print_table(int n)
{
    int i=0;
    for(i=1;i<=n;i++)
    {
        int j=0;
        for(j=1;j<=i;j++)
        {
            printf("%d*%d=%-3d,i,j,i*j);
        }
        printf(\n);
    }
}
int main()
{
    int n=0;
    scanf("%d",&n);
    print_table(n);
    return 0;
}

//字符串逆序
int my_strlen(char* str)
{
    int count=0;
    while(*str!='\0')
    {
        count++;
        str++;
    }
    return count;
}
void reverse_string(char arr[])
{
    int left=0;
    int right=my_strlen(arr)-1;

    while(left<right)
    {
      int tmp=arr[left];
      arr[left]=arr[right];
      arr[right]=tmp;
      left++;
      right--;
    }
}
int main()
{
    char arr[]="abcdef";//fedcba
    reverse_string(arr);
    printf("%s\n",arr);
    return 0;
}

//字符串逆序(递归实现)
void reverse_string(char arr[])
{
    char tmp=arr[0];
    int len=my_strlen(arr);
    arr[0]=arr[len-1];
    arr[len-1]='\0';
    //递归必须有限制条件,而且必须慢慢靠近这个条件
    if(my_strlen(arr+1)>=2)
    reverse_string(arr+1);
    arr[len-1]=tmp;
}
int main()
{
    char arr[]={abcdef";
    reverse_string(arr);
    printf("%s\n",arr);
    return 0;
}


//DigitSum(1729)
//DigitSum(172)+1729%10
//DigitSum(17)+172%10+1729%10
//DigitSum(1)+17%10+...
//1+7+2+9
int DigitSum(unsigned int num)
{
    if(num>9)
    {
        return DigitSum(num/10)+num%10;
    }
    else
    {
        return num;
    }
}
int main()
{
    unsigned int num=0;
    scanf("%d",&num);//1729
    int ret=DigtSum(num);
    printf("ret=%d\n",ret);
    return 0;
}


//编写一个函数实现n的k次方
double Pow(int n,int k)
{
    //n^k=n*n^(k-1)
    if(k<0)
        return (1.0/(Pow(n,-k)));
    else if(k==0)
        return  1;
    else
        return n*Pow(n,k-1);
}
int main()
{
    int n=0;
    int k=0;
    scanf("%d%d",&n,&k);
    double ret=Pow(n,k);
    printf("ret=%lf\n",ret);
    return 0;
}
