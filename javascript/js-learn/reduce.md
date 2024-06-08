# reduce()

### <mark style="color:green;">reduce()</mark>

> arr.reduce(callback(acc, cur, idx, arr), initialValue)
>
> 배열.reduce(callback(누적값, 현재값, 인덱스, 요소) , 초기값)

```javascript
const arr = [1, 2, 3, 4, 5]

arr.reduce((acc, cur, idx) => {
    return acc + cur
}, 0)

// 10
```

***

### <mark style="color:purple;">프로그래머스 개인정보 수집 유효기간</mark>

```javascript
terms = ["A 6", "B 12", "C 3"]
// terms 배열을 빈칸 기준으로 왼쪽을 키값, 
// 오른쪽을 밸류 값으로 가지는 객체를 만들고 싶어서 reduce 사용

terms = terms.reduce((acc, term) => {
    const [key, value] = term.split(' ')
    acc[key] = value
    
    return acc
}, {})


```
