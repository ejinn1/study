# Map

### <mark style="color:green;">Map의 특징</mark>

1. **키의 유형**: `Map`은 다양한 유형의 값을 키로 사용할 수 있습니다. 예를 들어, 객체, 함수, 기본 데이터 타입 등을 키로 설정할 수 있습니다.
2. **순서 유지**: `Map` 내의 요소들은 삽입된 순서대로 유지됩니다. 이로 인해 반복 작업 시 키-값 쌍이 추가된 순서대로 처리됩니다.
3. **키의 동일성**: `Map`에서 키의 동일성은 `===` 연산자를 통해 확인됩니다. 예외적으로 `-0`과 `+0`은 같은 키로 간주되며, `NaN`은 자기 자신과 동일하다고 간주됩니다.
4. **크기 측정**: `Map` 객체의 크기를 쉽게 확인할 수 있는 `size` 속성이 있습니다.



### <mark style="color:green;">기본 메소드</mark>

* **set(key, value)**: 키-값 쌍을 `Map`에 추가합니다. 이미 존재하는 키에 값을 설정하면 값을 업데이트합니다.
* **get(key)**: 주어진 키에 대한 값을 반환합니다. 키가 존재하지 않으면 `undefined`를 반환합니다.
* **has(key)**: `Map`이 주어진 키를 포함하고 있는지 확인합니다. 포함하고 있으면 `true`, 그렇지 않으면 `false`를 반환합니다.
* **delete(key)**: 주어진 키와 관련된 키-값 쌍을 `Map`에서 제거합니다. 성공적으로 제거되면 `true`, 실패하면 `false`를 반환합니다.
* **clear()**: `Map`의 모든 키-값 쌍을 제거합니다.



### <mark style="color:green;">반복 작업</mark>

`Map`은 반복 가능한 객체로, `for...of` 루프를 통해 키-값 쌍을 반복하여 접근할 수 있습니다. 또한 다음 세 가지 메소드를 통해 반복자를 얻을 수 있습니다:

* **keys()**: `Map`의 모든 키를 포함하는 반복자를 반환합니다.
* **values()**: `Map`의 모든 값을 포함하는 반복자를 반환합니다.
* **entries()**: `Map`의 모든 키-값 쌍을 포함하는 반복자를 반환합니다. 각 요소는 `[key, value]` 형태의 배열입니다.

```javascript
let map = new Map();

// 값 추가
map.set('name', 'John');
map.set('age', 30);

// 값 접근
console.log(map.get('name')); // "John"
console.log(map.get('age')); // 30

// 키 존재 여부 확인
console.log(map.has('name')); // true
console.log(map.has('address')); // false

// 반복 작업
for (let [key, value] of map.entries()) {
    console.log(key + ': ' + value);
}

// 크기 확인
console.log(map.size); // 2

```
