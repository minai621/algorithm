# 동적계획법
## 개념
특정 범위까지의 값을 구하기 위해서 그것과 다른 범위까지의 값을 이용하여 효율적으로 값을 구하는 알고리즘 설계 기법이다.
DP를 생각할 때는 테이블을 먼저 생각하면 좋다.
![dp table](https://wikidocs.net/images/page/170954/dp3.PNG)
이때 값을 저장하는 것을 메모이제이션이라고 한다. 
DP는 Top-down과 bottom-up이 있다. 
Top-down은 큰 문제부터 시작해서 작은 문제를 해결하여 답을 찾는다.
bottom-up은 작은 문제에서 테이블을 쌓아 큰 문제를 풀 수 있다. 