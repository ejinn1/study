# 재귀





***

### 예제

* **isPalindrome**\
  전달된 문자열이 팔린드롬(앞으로 읽으나 뒤로 읽으나 동일한 문자)인 경우 true 를 반환하는 **isPalindrome**이라는 재귀(recursive) 함수를 작성하시오. 팔린드롬이 아닐 경우 false 를 반환합니다.

```javascript
// isPalindrome('awesome') // false
// isPalindrome('foobar') // false
// isPalindrome('tacocat') // true
// isPalindrome('amanaplanacanalpanama') // true
// isPalindrome('amanaplanacanalpandemonium') // false

// 내 답
function isPalindrome(str){
  // add whatever parameters you deem necessary - good luck!
    if(str[0] !== str[str.length - 1]) return false
    if(str.length <= 3) return true
    return true && isPalindrome(str.slice(1,str.length - 1))
}

// 답
function isPalindrome(str){
    if(str.length === 1) return true;
    if(str.length === 2) return str[0] === str[1];
    if(str[0] === str.slice(-1)) return isPalindrome(str.slice(1,-1))
    return false;
}
```



* **someRecursive**\
  배열과 콜백을 받아들이는 **someRecursive** 라는 재귀(recursive) 함수를 작성하시오. 이 함수는 배열의 단일 값이 콜백에 전달될 때 true를 반환하면 true를 반환합니다. 그렇지 않으면 false를 반환합니다.

```javascript
// SAMPLE INPUT / OUTPUT
// const isOdd = val => val % 2 !== 0;

// someRecursive([1,2,3,4], isOdd) // true
// someRecursive([4,6,8,9], isOdd) // true
// someRecursive([4,6,8], isOdd) // false
// someRecursive([4,6,8], val => val > 10); // false

// 내 답
function someRecursive([...arr], callback){
  // add whatever parameters you deem necessary - good luck!
    if(callback(arr[0])) return true
    if(!callback(arr[0]) && arr.length === 1) return false
    return false || someRecursive(arr.slice(1), callback)
}

// 답
function someRecursive(array, callback) {
    if (array.length === 0) return false;
    if (callback(array[0])) return true;
    return someRecursive(array.slice(1),callback);
}
```



* **flatten**\
  배열의 배열을 받아들이고 모든 값이 평활화(flattened)된 새 배열을 반환하는 **flatten**이라는 재귀(recursive ) 함수를 작성합니다.

```javascript
// 답
function flatten(oldArr){
  var newArr = []
  for(var i = 0; i < oldArr.length; i++){
    	if(Array.isArray(oldArr[i])){
      		newArr = newArr.concat(flatten(oldArr[i]))
    	} else {
      		newArr.push(oldArr[i])
    	}
  } 
  return newArr;
}
```



* capitalizeFirst\
  **capitalizeFirst**라는 재귀 함수를 작성하시오.\
  문자열 배열이 주어지면 배열에 있는 각 문자열의 첫 글자를 대문자로 바꿔주는 함수입니다.

```javascript
// 내 답
function capitalizeFirst (arr) {
  // add whatever parameters you deem necessary - good luck!
  let newarr = []
  if(typeof arr === 'string'){
      return arr[0].toUpperCase()+arr.slice(1)
  }
  for(let i=0 ; i<arr.length ; i++){
      newarr.push(capitalizeFirst(arr[i]))
  }
  
  return newarr
}

// capitalizeFirst(['car','taco','banana']); // ['Car','Taco','Banana']

```



* nestedEvenSum\
  **nestedEvenSum**이라는 재귀 함수를 작성하시오. 중첩된(nested) 객체를 포함할 수 있는 객체에서 모든 짝수의 합계를 반환하는 함수입니다.

```javascript
// 내 답
function nestedEvenSum (obj) {
  // add whatever parameters you deem necessary - good luck!
    let sum = 0
    for(let key in obj){
        if(typeof obj[key] === 'number'){
            if(obj[key] % 2 === 0){
                sum += obj[key]
            }
        } else if(typeof obj[key] === 'object') {
            sum += nestedEvenSum(obj[key])
        }
        
    }

    return sum
}

var obj1 = {
  outer: 2,
  obj: {
    inner: 2,
    otherObj: {
      superInner: 2,
      notANumber: true,
      alsoNotANumber: "yup"
    }
  }
}

var obj2 = {
  a: 2,
  b: {b: 2, bb: {b: 3, bb: {b: 2}}},
  c: {c: {c: 2}, cc: 'ball', ccc: 5},
  d: 1,
  e: {e: {e: 2}, ee: 'car'}
};

nestedEvenSum(obj1); // 6
nestedEvenSum(obj2); // 10
```

```javascript
// 답
function nestedEvenSum (obj, sum=0) {
    for (var key in obj) {
        if (typeof obj[key] === 'object'){
            sum += nestedEvenSum(obj[key]);
        } else if (typeof obj[key] === 'number' && obj[key] % 2 === 0){
            sum += obj[key];
        }
    }
    return sum;
}
```



* capitalizeWords\
  **capitalizeWords**라는 재귀 함수를 작성하시오. 단어 배열이 주어지면 각 단어가 대문자로 표시된 새 배열을 반환합니다.

```javascript
// 내 답
function capitalizeWords(arr){
    let newArr = []
    if(typeof arr === 'string'){
        return arr.toUpperCase()
    }
    
    for(let i=0 ; i<arr.length ; i++){
        newArr.push(capitalizeWords(arr[i]))
    }

    return newArr
}

```

```javascript
function capitalizeWords (array) {
  if (array.length === 1) {
    return [array[0].toUpperCase()];
  }
  let res = capitalizeWords(array.slice(0, -1));
  res.push(array.slice(array.length-1)[0].toUpperCase());
  return res;
 
}
```



* stringifyNumbers\
  객체를 받아 숫자인 모든 값을 찾아 문자열로 변환하는 `StringifyNumbers`라는 함수를 작성하시오. 재귀(Recursion) 함수는 이 문제를 해결하는 좋은 방법이 될 것입니다!





*   collectStrings

    객체를 받아들이고 문자열에 해당하는 모든 값의 배열을 반환하는 `collectStrings`라는 함수를 작성합니다



```javascript
stringifyNumbers 솔루션

function stringifyNumbers(obj) {
  var newObj = {};
  for (var key in obj) {
    if (typeof obj[key] === 'number') {
      newObj[key] = obj[key].toString();
    } else if (typeof obj[key] === 'object' && !Array.isArray(obj[key])) {
      newObj[key] = stringifyNumbers(obj[key]);
    } else {
      newObj[key] = obj[key];
    }
  }
  return newObj;
}

collectStrings 솔루션: Helper 메소드 재귀 버전

function collectStrings(obj) {
    var stringsArr = [];
 
    function gatherStrings(o) {
        for(var key in o) {
            if(typeof o[key] === 'string') {
                stringsArr.push(o[key]);
            }
            else if(typeof o[key] === 'object') {
                return gatherStrings(o[key]);
            }
        }
    }
 
    gatherStrings(obj);
 
    return stringsArr;
}

collectStrings 솔루션: 순수 재귀 버전

function collectStrings(obj) {
    var stringsArr = [];
    for(var key in obj) {
        if(typeof obj[key] === 'string') {
            stringsArr.push(obj[key]);
        }
        else if(typeof obj[key] === 'object') {
            stringsArr = stringsArr.concat(collectStrings(obj[key]));
        }
    }
 
    return stringsArr;
}

```
