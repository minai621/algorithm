# 정수론

정수론은 정수를 다루는 한 분야이다.

## 소수와 인수

정수 a로 b가 나누어떨어지는 경우, a를 b의 인수(factor), 혹은 약수(divisor)라고 한다.
a가 b의 인수인 경우 a|b로 표기한다.
어떤 정수 n > 1에 대해 양의 인수가 1과 n 뿐이면 n을 소수(prime)이라고 한다.

## 기본 알고리즘

정수 n이 소수가 아니면 두 정수 곱 a \* b로 나타낼 수 있고, 이때 a <= sqrt(n)과 b <= sqrt(n)이 성립한다.
즉, 2 이상 [sqrt(n)]이하의 인수가 반드시 존재한다.

### 소수의 성질

소수를 유한하다고 가정하면 P1, P2, ... Pn + 1라는 집합 P가 있을 때,
이를 모두 곱한 수는 합성수 이므로 소인수분해가 가능해야 하지만 소수로 나누어 떨어지지 않고 1이 남기 때문에 모순이 생긴다. 따라서 소수는 무한하다.

### 에라토스테네스의 체

2 이상 n 이하의 정수 x가 소수인지 판별할 수 있도록 sieve 배열을 만드는 전처리 알고리즘이다.

```cpp
for(int x = 2; x <= n; x++) {
    if(sieve[x]) continue;
    for(int u = 2 * x; u <= n; u == x) {
        sieve[u] = 1;
    }
}
```

### 유클리드 알고리즘

정수 a와 b의 최대공약수(greatest common divisor) gcd(a,b)는 a와 b의 모두의 약수 중 가장 큰 정수를 말한다. 관련된 개념으로 최소공배수(lowest common multiple) lcm(a, b)가 있는데, 이는 a와 v로 모두 나누어떨어지는 가장 작은 정수를 말한다. 최소공배수를 계산하기 위해서 다음 공식을 활용할 수 있다.

lcm(a, b) = a\*b/gcd(a, b)

gcd를 구하는 법은 다음과 같다.

```cpp
int gcd(int a, int b) {
    if(b == 0) return a;
    return gcd(b, a%b);
}
```
