# exam
第一题
#include <stdio.h> 
int swap(char *s,char *p) 
{ 
   int i = 0; 
   char temp; 


   if(*++p != '\0') 
      i = swap(s,p); 
   if((s+i) <= (--p)) 
   { 
      temp = *(p); 
      *(p) = *(s+i); 
 *(s+i) = temp; 
   } 
   return ++i; 
} 


char *reverse(char *s) 
{ 
   char *p,*q; 


   q = p = s; 
   swap(q,p); 
   return s; 
} 

int main(void) 
{ 
   char s[] = "I want eat fish!"; 


   printf("%s\n",reverse(s)); 
   return 0; 
}
第二题
#include <stdio.h>
#include <ctype.h>

# define MAXLINE 1000

int getline(char s[], int lim)
{
	int c, i;
	i = 0;
	while(--lim > 0 && (c = getchar()) != EOF && c != '\n')
		s[i++] = c;
	if(c == '\n')
		s[i++] = c;
	s[i] = '\0';
	return i; 
} 

main(int argc, char *argv[])
{
	int c, i, ans;
	char s[MAXLINE];
	i = 0;
	getline(s, MAXLINE);
	while(--argc > 0 && isdigit(c = (*++argv)[0]) == 0)
	{
		if(i = 0)
			ans = c;
		switch(c)
		{
			case '+':
			{	
				ans = (*(argv - 2 - i))[0] + ans;
				i++;
				continue;
			}
			case '*':
			{
				ans = (*(argv - 2 - i))[0] * ans;
				i++;
				continue;
			}
		}
	}
	printf("%d ", ans); 
}
第三题
private static void mergeSort(int[] arr, int leftbound, int rightbound) {
        int i=leftbound;
        int j=(rightbound+leftbound)/2;
        int mid=j;
        int[] temp=new int[rightbound-leftbound];
        int t=0;
        while (i<mid&&j<rightbound){
            if (arr[i]<arr[j]){
                temp[t++]=arr[i++];
            }else {
                temp[t++]=arr[j++];
            }
        }
        while (i<mid) temp[t++]=arr[i++];
        while (j<rightbound) temp[t++]=arr[j++];
        for (int val:temp) {
            arr[leftbound]=val;
            leftbound++;
        }

    }
    第四题
    unique = () => {
	  let arr = [{
	    "name": "张三",
	    "serial": "0001"
	  }, {
	    "name": "李四",
	    "serial": "0002"
	  }, {
	    "name": "王五",
	    "serial": "0003"
	  }, {
	    "name": "王五2",
	    "serial": "0003"
	  }, {
	    "name": "赵四",
	    "serial": "0004"
	  }, {
	    "name": "小明",
	    "serial": "005"
	  }, {
	    "name": "小张",
	    "serial": "006"
	  }, {
	    "name": "小李",
	    "serial": "006"
	  }, {
	    "name": "小李2",
	    "serial": "006"
	  }, {
	    "name": "赵四2",
	    "serial": "0004"
	  }];
	  let newArr = [];
	  for (let item of arr) {
	    const { serial = '' } = item;
	    const aaa = newArr.find(item => item.serial === serial);
	    if (!aaa) {
	      newArr.push(item);
	    }
	  }
	  return newArr;
	}
    第五题
    var tree = [
	  {
      "id": "1",
      "name": "中国",
      "code": "110",
      "parent": ""
    },
    {
      "id": "2",
      "name": "北京市",
      "code": "110000",
      "parent": "110"
    },
    {
      "id": "3",
      "name": "河北省",
      "code": "130000",
      "parent": "110"
    },
    {
      "id": "4",
      "name": "四川省",
      "code": "510000",
      "parent": "110"
    },
    {
      "id": "5",
      "name": "石家庄市",
      "code": "130001",
      "parent": "130000"
    },
    {
      "id": "6",
      "name": "唐山市",
      "code": "130002",
      "parent": "130000"
    },
    {
      "id": "7",
      "name": "邢台市",
      "code": "130003",
      "parent": "130000"
    },
    {
      "id": "8",
      "name": "成都市",
      "code": "510001",
      "parent": "510000"
    },
    {
      "id": "9",
      "name": "简阳市",
      "code": "510002",
      "parent": "510000"
    },
    {
      "id": "10",
      "name": "武侯区",
      "code": "51000101",
      "parent": "510001"
    },
    {
      "id": "11",
      "name": "金牛区",
      "code": "51000102",
      "parent": "510001"
    }
	];
	
	transDate = (tree, idstr = 'id', pidstr = 'parent') => {
	  let result = [], temp = {};
	  for (i = 0; i < tree.length; i++) {
	    temp[tree[i][idstr]] = tree[i];
	  }
	  for (j = 0; j < tree.length; j++) {
	    tempVp = temp[tree[j][pidstr]];
	    if (tempVp) {
	      if (!tempVp["nodes"]) tempVp["nodes"] = [];
	      tempVp["nodes"].push(tree[j]);
	    } else {
	      result.push(tree[j]);
	    }
	  }
	  return result;
	}
