```
cf Shortest path of the king
算法---数学知识：切比雪夫距离
棋盘上算两点之间的最短可到达距离===包括斜着走，要不然不一定可以用
代码：
#include<bits/stdc++.h>
using namespace std;
string s1,s2;
int main()
{
	cin>>s1>>s2;
	int x1=s1[0]-'a'+1,y1=s1[1]-'0',x2=s2[0]-'a'+1,y2=s2[1]-'0';//计算两个点的坐标
	int dis=max(abs(x1-x2),abs(y1-y2));//计算两点的切比雪夫距离
	printf("%d\n",dis);
	while(dis--)
	{
		if(x1>x2 && y1>y2){x1--;y1--;printf("LD\n");continue;}//判断一下
		if(x1>x2 && y1==y2){x1--;printf("L\n");continue;}
		if(x1>x2 && y1<y2){x1--;y1++;printf("LU\n");continue;}
		if(x1==x2 && y1>y2){y1--;printf("D\n");continue;}
		if(x1==x2 && y1<y2){y1++;printf("U\n");continue;}
		if(x1<x2 && y1>y2){x1++;y1--;printf("RD\n");continue;}
		if(x1<x2 && y1==y2){x1++;printf("R\n");continue;}
		if(x1<x2 && y1<y2){x1++;y1++;printf("RU\n");continue;}
	}
}
```
