
# 제목 1
### [popper.js](https://popper.js.org/)
### [bootstrap](https://getbootstrap.com/docs/5.2/getting-started/introduction/)
## bootstrap 설치
npm i bootstrap@5.2.2

## main.scss파일
### @import "../node_modules/bootstrap/scss/bootstrap.scss"
node_modeules 라는 폴더에 접근할수 없기 때문에 상대경로로 node_modeules폴더를 찾아 접근 시킨다.

### bootstrap 에서 필수로 사용하는 scss 함수들
```css
@import "../node_modules/bootstrap/scss/functions";
@import "../node_modules/bootstrap/scss/variables";
@import "../node_modules/bootstrap/scss/mixins";
```

## 테마 색상 커스터마이징
### bootstrap 에서 지정되어 있는 색상 변경
[bootstrap color 변경 참고사이트](https://getbootstrap.com/docs/5.2/customize/color/) <br>
```css
$theme-colors: ( 
  "primary":    $primary,
  "secondary":  $secondary,
  "success":    $success,
  "info":       $info,
  "warning":    $warning,
  "danger":     $danger,
  "light":      $light,
  "dark":       $dark
);
```
## 로딩 애니메이션 처리
[참고 사이트](https://getbootstrap.com/docs/5.2/components/spinners/#about)



## main.js 파일
```js
import bootstrap from 'bootstrap/dist/js/bootstrap.bundle'
```
node_modeules 라는 폴더에 설치 되어져 있는 bootstrap 폴더로 접근이 가능함 (js만 가능)

## 성능 최적화(트리 쉐이킹)
[Optimize](https://getbootstrap.com/docs/5.2/customize/optimize/#lean-sass-imports)

## main.js파일
```js
//사용하려는 bootstrap 기능에는 컴포넌트 초기화를 시켜줘야 하는것이 있고 없는것도 있음

import bootstrap from 'bootstrap/dist/js/bootstrap.bundle' //모든 bootstrap 기능 지정

import Dropdown from 'bootstrap/js/dist/dropdown' //사용하려는 기능만 지정 

const dropdownElementList = document.querySelectorAll('.dropdown-toggle')
const dropdownList = [...dropdownElementList].map(dropdownToggleEl => new Dropdown.Dropdown(dropdownToggleEl))

//import bootstrap from 'bootstrap/dist/js/bootstrap.bundle'
import Modal from 'bootstrap/js/dist/modal'

new Modal('#exampleModal', {backdrop:'static'})
```

