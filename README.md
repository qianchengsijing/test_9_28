# test_9_28
#include <stdio.h>

//栈的顺序存储
#define MaxSize 50
typedef struct {
	int data[MaxSize];
	int top;
}SqStack;

void InitStack(SqStack &S){
	S.top = -1;
}
bool StackEmpty(SqStack S){
	if(S.top == -1)
		return true;
	else
		return false;
}
bool Push(SqStack &S,int x){
	if(S.top == MaxSize-1)
		return false;
	S.data[++S.top] = x;
	return true;
}
bool Pop(SqStack &S,int &x){
	if(S.top == -1)
		return false;
	x = S.data[S.top--];
	return true;
}
bool Gettop(SqStack S,int &x){
	if(S.top == -1)
		return false;
	x = S.data[S.top];
	return true;
}
int main(){
	SqStack S;
	InitStack(S);
	StackEmpty(S);
	Push(&S,x);
	Pop(&S,&x);
	Gettop(S,&x);
	return 0;
}
#define MaxSize 10
typedef struct{
	int data[MaxSize];
	int top0;
	int top1;
}ShStack;
void InitStack(ShStack &S){
	S.top0 = -1;
	S.top1 = MaxSize;
}
void testStack(){
	ShStack S;
	InitStack(&S);
}
//链栈
typedef struct LinkNode{
	int data;
	struct LinkNode* next;
}*LiStack;

int judge(char A[]){
	int i=0;
	int j,k=0;
	while(A[i] != '\0'){
		switch(A[i]){
			case 'I':j++;break;
			case 'O':k++;
				if(k>j)
					printf("序列非法\n");
		}
		i++;
	}
	if(j != k){
		printf("序列非法\n");
	    return false;
	}
	else{
		printf("序列合法\n");
		return true;
	}
}
