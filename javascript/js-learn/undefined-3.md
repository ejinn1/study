# 문자열 정렬

### 문자열 정렬

```javascript
let countries = ["Germany", "France", "Japan", "Korea", "Australia", "United States"]

countries.sort((a, b) => a.localeCompare(b))

console.log(countries)
// ['Australia', 'France', 'Germany', 'Japan', 'Korea', 'United States']

```



### 문자 집합 만들어서 정렬

* str.substring(start, end)

```javascript
// 문자열 만들기
function getAllSubstrings(s) {
    let substrings = new Set();
    let length = s.length;

    for (let i = 0; i < length; i++) {
        for (let j = i + 1; j <= length; j++) {
            substrings.add(s.substring(i, j));
        }
    }

    return Array.from(substrings);
}

// k번째 순서
function kthSubstring(s, k) {
    let substrings = getAllSubstrings(s);
    substrings.sort();

    return substrings[k - 1] || null; // k가 배열의 길이를 넘으면 null 반환
}
```

