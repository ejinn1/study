# 스크롤 바 숨기기

```css
body{
 -ms-overflow-style: none;
 }
 
::-webkit-scrollbar {
  display: none;
}

/*특정 부분 스크롤바 없애기*/

.box{
   -ms-overflow-style: none;
}
.box::-webkit-scrollbar{
  display:none;
}
출처: https://wooaoe.tistory.com/49 [개발개발 울었다:티스토리]
```
