# 검색

### 선형 검색

\-> 한번에 하나씩 비교하면서 검색한다

#### js 기본 선형검색 메소드

* indexOf
* includes
* find
* findIndex

### 이진 검색

예시코드

```javascript
function binarySearch(arr, target){
  // add whatever parameters you deem necessary - good luck!
    let start = 0
    let end = arr.length - 1
    while(start <= end){
        let mid = Math.floor((start + end) / 2)
        if(arr[mid] < target){
            end = mid - 1
        } else {
            start = mid + 1
        }
    }
    
    return arr[mid] === target ? mid : -1
}
```



### naive 문자열 검색

long 문자열에서 short문자열이 몇 개 있는지 검색

```javascript
function naiveSearch(long, short){
    let cnt = 0
    for(let i=0 ; i<long.length ; i++){
        for(let j=0 ; j<short.length ; j++){
            // 이 방법은 처음 알음
            if(long[i+j] !== short[j])){
                break
            }
            if(j === short.length - 1){
                cnt++
            }
        }
    }

    return cnt
}
```
