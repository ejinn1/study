# splice()

### <mark style="color:green;">splice()</mark>

> arr.splice(start, deleteCount, ...item)
>
> 배열.splice(시작 인덱스, 삭제할 요소 개수, 추가할 요소 배열)

배열에서 특정 값 삭제or 추가할 때 사용

```javascript
let arr = [1,2,3,4,5]

// 삭제
arr.splice(2, 1) // [1,3,4,5]

// 추가
arr.splice(3, 0, 7) // [1,3,4,7,5]
```
