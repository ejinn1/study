# Date

> [https://ko.javascript.info/date](https://ko.javascript.info/date)

### 객체 생성

#### new Date()

```javascript
let now = new Date()
console.log(now) // "2024-05-07T04:46:45.039Z"
```

#### new Date(milliseconds)

* UTC 시준 1970년 1월 1월 0시 0분 0초에서 밀리초 후의 시점이 저장

```javascript
let stand = new Date(0)
console.log(stand) // "1970-01-01T00:00:00.000Z"
```

#### new Date(datestring)

```javascript
let date = new Date("2024-05-07")
console.log(date) // "2024-05-07T00:00:00.000Z"

// Tue May 07 2024 09:00:00 GMT+0900 (한국 표준시)
```

#### new Date(year, month, date, hours, minutes, seconds, ms)

* year은 4자리 숫자
* month는 0_(1월)_ \~ 11_(12월)_ 까지
* date는 값이 없을 떈 1일로 처리
* hour, minutes, seconds, ms는 값이 없으면 0으로 처리

```javascript
let date = new Date(2024,4,7)
console.log(date) // "2024-05-06T15:00:00.000Z"

// Tue May 07 2024 09:00:00 GMT+0900 (한국 표준시)
// UTC 기준으로 반환되어서 콘솔에 있는 객체 복사하면 날짜가 바뀜 (?)
// date.toLocalestring() 붙히면 로컬 기준으로 변경되서 출력됨
```

***

### 날짜 구성요소

#### getFullYear()

#### getMonth()

#### getDate()

#### getHours(), getMinutes(), getSeconds(), getMilliseconds()

#### getDay()

* 0 -> 일요일, 6 -> 토요일

***

### 날짜 구성요소 설정

메서드 인수에 없는 구성요소는 변경되지 않는다

* `setFullYear(year, [month], [date])`
* `setMonth(month, [date])`
* `setDate(date)`
* `setHours(hour, [min], [sec], [ms])`
* `setMinutes(min, [sec], [ms])`
* `setSeconds(sec, [ms])`
* `setMilliseconds(ms)`
* `setTime(milliseconds)`&#x20;

***

### 자동고침

```javascript
let date = new Date(2024, 0, 32) // 2024년 2월 1일
date.setSeconds(date.getSeconds() + 70) // 70초 후의 날짜
```

***

### Date.now()









### Date.parse









