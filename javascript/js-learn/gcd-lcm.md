# GCD, LCM

### <mark style="color:green;">최대공약수</mark>

#### 기본

```javascript
function GCD(n, m){
    let gcd = 1
    for(let i=2 ; i<=Math.min(n, m) ; i++){
        if(n%i === 0 && m%i === 0){
            gcd = i
        }
    }
    
    return gcd
}
```

#### 유클리드 호제법

```javascript
function gcd(a, b) {
    while (b !== 0) {
        let temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

```

***

### <mark style="color:green;">최소공배수</mark>

#### 기본

```javascript
function LCM(n, m){
    let lcm = 1
    while(true){
        if(lcm%n === 0 && lcm%m === 0){
            break
        }
        lcm++
    }
    return lcm
}
```

#### GCD를 사용한 최소공배수

```javascript
function lcm(a, b) {
    return (a * b) / gcd(a, b);
}
```
