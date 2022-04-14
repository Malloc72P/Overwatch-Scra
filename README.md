# 오버워치 예제를 하면서 배운 것들

### 배포 링크
- [오버워치 영웅선택창 바로가기](https://malloc72p.github.io/Overwatch-Scra/)
### 마진을 사용한 가운데 정렬
```css
.container .logo {
  max-width: 300px;
  padding: 0 20px;
  margin: 0 auto;
}
```
- 요소에 가로 너비가 있을 때, 수평으로 `margin:auto`를 주면 가운데 정렬이 된다

### skew 복원
- 부모요소는 skew함수로 변형시키고, 자식 요소는 변형시키고 싶지 않다면, 자식요소만 반대방향으로 skew함수를 사용해서 변형시키면 된다.
- 부모요소
  ```css
  .container .heroes .hero {
    ...
    transform: skewX(-14deg);
  }
  ```
- 자식요소
  ```css
  .container .heroes .hero .image {
    ...
    transform: skewX(14deg) translateX(-16px);
  }
  ```

### 전환효과 다르게 주기
- 배경색상과 크기속성의 전환시간을 다르게 하면 좀 이뻐보인다(개인적인 느낌이긴 함)
  ```css
  transition:
      transform .1s,
      background-color .6s;
  ```
- 이렇게 하면 배경색상의 전환효과만 0.6s가 걸린다.
- 오버워치 예제의 경우, `scale()`함수에 의해 영웅 카드의 크기가 커지는 시간보다, 배경색상이 변하는 시간이 더 오래 걸린다.
- 그래서 카드의 크기가 커진 다음, 배경색상이 뒤따라서 변하는데, 개인적으로 이게 마음에 든다.
