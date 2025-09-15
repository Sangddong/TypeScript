# MAPPED TYPE
### 0. What is Mapped type?
- 기존에 정의되어 있는 타입을 새로운 타입으로 변환해주는 문법
- 자바스크립트의 `map()`을 사용한듯한 효과
<br>

``` typescripts
type Hero = 'Hulk' | 'Capt' | 'Thor';
type HeroAges = { [Key in Hero]: number };

const ages: HeroAges = {
  Hulk: 10;
  Capt: 10;
  Thor: 30;
};

```
