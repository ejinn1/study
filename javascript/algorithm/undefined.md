# 문제 접근

### 문제 해결 접근법

1. **문제 이해**
2. **구체적 예제 생각하기**
   1. 간단한 예제
   2. 복잡한 예제
   3. 빈 값
   4. 유효한 값
3. **세부 분석**
4. **해결 or 단순화**
   1. 단순화 시켜서 어려운부분은 나중에 해결하고 해결할 수 있는 부분 먼저 해결한다
5. **되돌아보기, 리펙토링**

<div align="left">

<figure><img src="../.gitbook/assets/image (1).png" alt="" width="375"><figcaption></figcaption></figure>

</div>

***

### 문제 해결 패턴

#### 빈도 수 세기

```javascript
// O(n)으로 풀기
function same(arr1, arr2) {
    let counter1 = {}
    let counter2 = {}

    for(let a of arr1){
        counter1[a] = ++counter1[a] || 1
    }
    for(let a of arr2){
        counter2[a] = ++counter2[a] || 1
    }

    for(let key in counter1){
        if(!(key ** 2 in counter2)){
            return false
        }
        if(counter2[key ** 2] !== counter1[key]){
            return false
        }
    }
    return true
}

same([1, 2, 3], [4, 9, 1])

```

* 애너그램

```javascript
function same(str1, str2) {
    let counter1 = {}
    let counter2 = {}

    str1 = [...str1]
    str2 = [...str2]

    for(let a of str1){
        counter1[a] = ++counter1[a] || 1
    }
    for(let a of str2){
        counter2[a] = ++counter2[a] || 1
    }

    console.log(counter1)
    console.log(counter2)

    for(let key in counter1){
        if(counter2[key] !== counter1[key]){
            return false
        }
    }
    return true
}

same("aavv", "vaav")

```

```javascript
// solution
function same(str1, str2) {
    if(str1.length !== str2.length) return false

    let obj = {}

    for(let i=0 ; i<str1.length ; i++){
        let ch = str1[i]
        obj[ch] ? obj[ch]++ : obj[ch] = 1
    }

    for(let i=0 ; i<str2.length ; i++){
        let ch = str2[i]
        if(!obj[ch]){
            return false
        } else {
            obj[ch] -= 1
        }
    }

    return true
}

same("aavv", "vaav")

```

***

### 다중 포인터

```javascript
function countUniqueValue(arr){
    return new Set(arr).size
}
```

```javascript
// solution

function countUniqueValue(arr){
    let j = 0
    for(let j = 0 ; j < arr.length ; j++){
        if(arr[i] !== arr[j]){
            i++
            arr[i] = arr[j]
        }
    }
    
    return i + 1
}
```

***

### 슬라이딩 윈도우

```javascript
function maxSubarraySum(arr, sum) {
    let tmpSum = 0 
    let maxSum = 0

    if(arr.length < num) return null
    
    for(let i=0 ; i<num ; i++){
        maxSum += arr[i]
    }
    tmpSum = maxSum
    for(let i = num ; i < arr.length ; i++){
        tmpSum = tmpSum - arr[i - num] + arr[i]
        maxSum = Math.max(tmpSum, maxSum)
    }

    return maxSum
}

```

***

### 분할과 정복

```javascript
// 이분탐색
function search(arr, val){
    let min = 0
    let max = arr.length - 1

    while (min <= max)) {
        let middel = Math.floor((min + max) / 2)
        let currentVal = arr[middle]

        if(currentVal > val){
            min = middle + 1
        } else if(currentVal < val){
            max = middle - 1
        } else {
            return middle
        }
    }
    return -1
}
```

