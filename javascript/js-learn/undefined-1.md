# 대문자, 소문자 변환

### <mark style="color:green;">toUpperCase()</mark>

> str.toUpperCase()
>
> 문자열.toUpperCase()

소문자를 대문자로 바꾸어준다.

```javascript
let str = 'abc'

console.log(str.toUpperCase()) // ABC
```

### <mark style="color:green;">toLowerCase()</mark>

> str.toLowerCase()
>
> 문자열.toLowerCase()

대문자를 소문자로 바꾸어준다.

```javascript
let str = 'ABC'

console.log(str.toLowerCase()) // abc
```

***

#### <mark style="color:blue;">문자열에 문자가 아닌 값이 있을 떄</mark>

```javascript
let str = '123_.def'

console.log(str.toUpperCase()) // 123_.DEF
// 그냥 냅둠
```

