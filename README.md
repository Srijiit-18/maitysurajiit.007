#include<stdio.h>
#define MAXSIZE 5
int f = -1;
int r = -1;

void QPush(int queue[]){
	int data;
	if( f == -1){
		printf("Enter the Element\n");
		scanf("%d",&data);
		queue[++r] = data;
		++f;
	}
	else if(r == MAXSIZE-1){	
		printf("OverFlow\n");
	}	
	else{
		printf("Enter the Element\n");
		scanf("%d",&data);
		queue[++r] = data;
	}
}
int QPop(int queue[])
{
	if(f == -1){
		printf("Queue is Empty\n");
		return -1;
	}
	int item = queue[f];
	if( f == r){
		f == r == -1;
		return item;
	}
	else
		return queue[f++];
}
void QPeek(int queue[]){
	if(f == -1)
	printf("Queue is Empty\n");
	else{
		for(int i = f; i<=r; i++)
		{
			printf(" %d ",queue[i]);
		}
		printf("\n");
	}
}
void main(){
	int queue[MAXSIZE];
	int ch;
	do{
		printf("\n");
		printf("1. Push Operation in Queue\n2. Pop Operation in Queue\n3. Peek Operation in Queue\n4. Exit\n");
		printf("Enter Your Choice\n");
		scanf("%d",&ch);
		switch(ch){
			case 1:
				QPush(queue);
				break;
			case 2:
				QPop(queue);
				break;
			case 3:
				QPeek(queue);
				break;
			case 4:
				printf("Exiting from the code.....\n");
				break;
			default:
				printf("Wrong Choice\n");
				break;
		}
	}while(ch != 4);
}
