<!-- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty -->

Object.defineProperties()

- 객체 동작 재정의
- vue-way.html 확인

즉시 실행 함수

- [IIFE - MDN Web Docs 용어 사전: 웹 용어 정의 | MDN](https://developer.mozilla.org/ko/docs/Glossary/IIFE)



## Vue 란?

MVVM 패턴의 뷰모델 레이어에 해당하는 화면 라이브러리<br>

```v
//객체의 동작 재정의 하는 api
//Object.defineProperty(대상객체, 객체의 속성, {
//            정의할 내용      
//})

Object.defineProperty(viewModel, 'str', {
    // 속성에 접근했을 때의 동작 정의
    get: function() {
        console.log('접근')
    },
    // 속성에 값을 할당했을 때의 동작을 정의
    set: function(newValue) {
        console.log('할당', newValue)
        div.innerHTML = newValue;
    }
})
```

### reactivity : data의 변화에 따라 즉시 화면의 값이 바뀜

## 

## 뷰 인스턴스

인스턴스는 뷰로 개발할 때 필수로 생성해야 하는 코드입니다.<br>

### 인스턴스 생성

인스턴스는 아래와 같이 생성할 수 있습니다.<br>

```v
new Vue();
```

인스턴스를 생성하고 나면 아래와 같이 인스턴스 안에 어떤 속성과 API가 있는지 콘솔 창에서 확인할 수 있습니다.<br>

```v
var vm = new Vue();
console.log(vm);
```

### 인스턴스의 속성, API들

인스턴스에서 사용할 수 있는 속성과 API는 다음과 같습니다.<br>

```v
new Vue({
  el: ,
  template: ,
  data: ,
  methods: ,
  created: ,
  watch: ,
});
```

- el : 인스턴스가 그려지는 화면의 시작점 (특정 HTML 태그)
- [template](https://joshua1988.github.io/vue-camp/vue/template.html) : 화면에 표시할 요소 (HTML, CSS 등)
- data : 뷰의 반응성(Reactivity)이 반영된 데이터 속성
- [methods](https://joshua1988.github.io/vue-camp/syntax/methods.html) : 화면의 동작과 이벤트 로직을 제어하는 메서드
- [created](https://joshua1988.github.io/vue-camp/vue/life-cycle.html) : 뷰의 라이프 사이클과 관련된 속성
- [watch](https://joshua1988.github.io/vue-camp/syntax/watch.html) : data에서 정의한 속성이 변화했을 때 추가 동작을 수행할 수 있게 정의하는 속성

## 뷰 컴포넌트

컴포넌트는 화면의 영역을 구분하여 개발할 수 있는 뷰의 기능입니다. 컴포넌트 기반으로 화면을 개발하게 되면 코드의 재사용성이 올라가고 빠르게 화면을 제작할 수 있습니다.<br>

![image](https://user-images.githubusercontent.com/82499591/172050774-f5f1e325-5d92-439d-8110-433b5825b792.png)

### 컴포넌트 생성 코드 형식

컴포넌트를 생성하는 코드 형식은 아래와 같습니다.<br>

```v
// 전역 컴포넌트
Vue.component('컴포넌트 이름', {
  // 컴포넌트 내용
});
```

```v
// 지역 컴포넌트
new Vue({
    el: "#app",
    components: {
        // '컴포넌트 이름': '내용'
    }
});
```

## 컴포넌트 통신 방식

뷰 컴포넌트는 각각 고유한 데이터 유효 범위를 갖습니다. 따라서, 컴포넌트 간에 데이터를 주고 받기 위해선 아래와 같은 규칙을 따라야 합니다.

<img title="" src="https://user-images.githubusercontent.com/82499591/172054716-f5011764-f0ef-444f-81e4-2e77b484111d.png" alt="image" width="404">

## props

```v
<app-header v-bind:프롭스 속성 이름="상위 컴포넌트의 데이터 이름"></app-header>
```

## 이벤트 발생

이벤트 발생은 컴포넌트의 통신 방법 중 하위 컴포넌트에서 상위 컴포넌트로 통신하는 방식입니다.<br>

### 이벤트 발생 코드 형식

하위 컴포넌트의 메서드나 라이프 사이클 훅과 같은 곳에 아래와 같이 코드를 추가합니다.<br>

```v
// 하위 컴포넌트의 내용
this.$emit('이벤트 명');
```

## 뷰 라우터

뷰 라우터는 뷰 라이브러리를 이용하여 싱글 페이지 애플리케이션을 구현할 때 사용하는 라이브러리<br>

## 액시오스

뷰에서 권고하는 HTTP 통신 라이브러리는 액시오스(Axios)입니다. Promise 기반의 HTTP 통신 라이브러리이며 상대적으로 다른 HTTP 통신 라이브러리들에 비해 문서화가 잘되어 있고 API가 다양합니다.<br>

### Vue Cli  설치

```powershell
node -v
npm -v
npm install -g @vue/cli
```
