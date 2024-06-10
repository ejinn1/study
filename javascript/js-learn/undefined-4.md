# 거리 계산

### <mark style="color:green;">절대값을 이용한 거리 계산 (맨해튼 거리)</mark>

두 점 사이의 수직 및 수평 거리의 합

```javascript
const disL = Math.abs(left[0] - key[0]) + Math.abs(left[1] - key[1]);
const disR = Math.abs(right[0] - key[0]) + Math.abs(right[1] - key[1]);
```

### <mark style="color:green;">유클리드 거리의 제곱 계산</mark>

점 사이의 직선 거리를 계산, 피타고라스 정리를 사용하여 계산

```javascript
const disL = (left[0] - key[0])**2 + (left[1] - key[1])**2;
const disR = (right[0] - key[0])**2 + (right[1] - key[1])**2;
```

***

### <mark style="color:purple;">**적용 사례**</mark>

**맨해튼 거리**

* 주로 격자 기반의 문제에서 사용
* 도시의 거리 계산 또는 체스판에서의 이동 거리 계산에 적합

**유클리드 거리**

* 두 점 사이의 실제 직선 거리가 중요한 경우에 사용
* GPS를 이용한 두 위치 간의 실제 거리 계산에 적합
