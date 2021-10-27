#include<stdio.h>
#include<string.h>
#include<conio.h>
#define MAX 100
void input(int &n,float a[]){
	do{
		printf("Enter the values of the array:");
		scanf("%d",&n);
		if(n>MAX||n<0) printf("Enter again: ");
	}while(n>MAX||n<0);
	for(int i=0;i<n;i++){		
		printf("\nEnter a[%d]=",i);
		scanf("%f",&a[i]);
	}	
}
float handle(int n, float a[]){
	float max=a[0];
	for(int i=0;i<n;i++){
		if(max<a[i+1]) max=a[i+1];
	}
	return max;
}
void output(int n, float a[]){
	printf("\nValues of Array are:  ");
	for(int i=0;i<n;i++) {
		printf("%10.3f",a[i]);
	}
}
int main(){
	int n;
	float a[MAX];
	input(n,a);
	output(n,a);
	float max=handle(n,a);
	printf("\n\n\tMax value of Array is: %.3f",max);
	getch();
	return 0;
}
