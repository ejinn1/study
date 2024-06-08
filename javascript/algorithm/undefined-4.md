# 동적프로그래밍









***

### 예시

* 피보나치

```javascript
// 재귀 O(n^2)
function fibo(n){
    if(n <= 2) return 1
    return fibo(n-2) + fibo(n-1)
}

// memo (하향식) O(n)
function fibo(n, memo = {}) {
    if(memo[n] !== undefined) return memo[n]
    if(n <= 2) return 1
    let res = fibo(n-2, memo) + fibo(n-1, memo)
    memo[n] = res
    return res
}

// 타뷸레이션 (상향식) O(n)
// 공간 활용도가 좋다
function fibo(n){
    if(n <= 2) return 1
    let fibNums = [0, 1, 1]
    for(let i=3 ; i<=n ; i++){
        fibNums[i] = fibNums[i-1] + fibNums[i-2]
    }
    return fibNums[n]
}

```



