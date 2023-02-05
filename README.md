# permutation-cycle_-순열사이클
# c
첫째 줄에 테스트 케이스의 개수 T가 주어진다. 각 테스트 케이스의 첫째 줄에는 순열의 크기 N 이 주어진다. 둘째 줄에는 순열이 주어지며, 각 정수는 공백으로 구분되어 있다. 입력으로 주어진 순열에 존재하는 순열 사이클의 개수를 출력하는 프로그램을 작성해보자!

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int test[100];
int answer[100];

void dfs(int i){
	if(test[i]){
		return;}
	test[i]=1;
	dfs(answer[i]);
}


int main(){
	int cnt,j,i,t,n,k;
	scanf("%d",&t);
	k=0;
	while(k!=t){
		scanf("%d",&n);
	    for(i=1;i<=n;i++){
	    	scanf("%d",&answer[i]);
	    	test[i]=0;}
		cnt=0;
		for(j=1;j<=n;j++){
			if(test[j]==0){
				dfs(j);
				cnt++;}}
		printf("순열 사이클 갯수: %d\n",cnt);
		k++;}
    return 0;
}
