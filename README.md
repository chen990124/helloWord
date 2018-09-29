# helloWord
#include<stdio.h>
int main()
{
int y,m,d,er,term,x,r,d2;
int days(int moon,int er);
int eryue(int year);
printf("请输入年/月/日\n");
scanf("%d/%d/%d",&y,&m,&d);
for(r=1,term=0;r<y;++r)
{
er=eryue(r);
d2=days(13,er);
term=term+d2;
}
er=eryue(y);
d2=days(m,er);
term=term+d2+d;
x=term%7;
switch(x)
{
case 1:printf("星期六");break;
case 2:printf("星期日");break;
case 3:printf("星期一");break;
case 4:printf("星期二");break;
case 5:printf("星期三");break;
case 6:printf("星期四");break;
case 0:printf("星期五");break;
}

return 0;
}
int eryue(int year)
{
int r;
if((year%4==0&&year%100!=0)||year%4000==0)
r=29;
else
r=28;
return r;
}
int days(int moon,int e)
{
int sum=0;
switch(moon)
{
case 13:sum+=31;
case 12:sum+=30;
case 11:sum+=31;
case 10:sum+=30;
case 9:sum+=31;
case 8:sum+=31;
case 7:sum+=30;
case 6:sum+=31;
case 5:sum+=30;
case 4:sum+=31;
case 3:sum+=e;
case 2:sum+=31;
case 1:break;
}
return sum;
}
