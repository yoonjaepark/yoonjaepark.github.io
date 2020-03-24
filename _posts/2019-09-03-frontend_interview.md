---
layout: post
title: "프론트엔드 인터뷰 간단 정리"
author: "YoonJae"
description: "프론트엔드 인터뷰 간단 정리 | 초보개발자 기술 블로그"
image: ""
---

# javascript 정리

1. [es5 와 es6 차이](#es5-와-es6-차이)
1. [let, const, var 차이](#let,-const,-var-차이)
1. [스코프란?](#스코프란?)
1. [스코프 체인이란?](#스코프-체인이란?)
1. [호이스팅이란?](#호이스팅이란?)
1. [클로저란?](#클로저란?)
1. [이벤트 버블링, 캡쳐링, 위임](#이벤트-버블링,-캡쳐링,-위임)
1. [오버라이딩, 오버로딩 차이?](#오버라이딩,-오버로딩-차이?)
1. [argument와 parameter](#argument와-parameter)


### es5 와 es6 차이

- let, const 추가
- arrow function 추가
- class 추가
- 템플릿 리터럴(Template literal) 백 틱(`)으로 감싸진 문자열
- 함수 매개변수의 디폴트 값 설정 
- 제너레이터(Generator)
- 프로미스(Promise)
- async/await

### let, const, var 차이

var 함수 스코프, 재할당, 재선언 가능합니다.
let, const 블럭 스코프, 재선언 불가합니다.
const는 재할당도 불가 let은 재할당 가능합니다.

### 스코프란?

변수의 유효 범위이다. 전역, 함수, 블록 스코프가 있습니다. 전역 유효범위는 스크립트 전체에서 참조되는 것을 의미하는데, 말 그대로 스크립트 내 어느 곳에서든 참조됩니다. 함수 유효범위는 정의된 함수 안에서만 참조되는 것을 의미하며, 함수 밖에서는 참조하지 못합니다. 블록 스코프는 블록 내에서만 참조되는 것을 의미하며 블록 밖에서는 참조하지 못합니다. 하위에서 상위 스코프의 변수를 접근하는 것을 스코프 체인이라 합니다.

### 스코프 체인이란?

내부함수에서 상용하는 변수는 자신의 스코프 내에서 변수를 찾아서 없으면 상위 스코프로 찾아서 접근하는것입니다.

### 호이스팅이란?

말그대로 끌어올림 입니다.
변수의 선언을 스코프의 최상단으로 끌어올려주는것입니다. 예를 들면 함수 내에서 변수를 먼저 로그를 출력하고 그 밑에 부분에 선언을 하면 호이스팅되면서 내부적으로 선언을 해당 함수 스코프의 최상위에서 선언되어 undefined 가 출력 되는것 입니다. let/const선언 변수는 호이스팅되지 않는 것이 아니다. 스코프에 진입할 때 변수가 만들어지지만, 코드 실행이 변수가 실제 있는 위치에 도달할 때까지 액세스할 수 없는 것입니다.

### 클로저란?

외부함수에서 선언된 변수를 함수 내부에서 사용할 때 클로저가 생겨납니다. 외부 함수안에 리턴 함수를 작성하여 외부 함수를 전역 스코프에서 실행했을때 현재 실행 컨텍스트와 관련 없는 외부 함수의 변수를 참조 하는 함수를 클로저라고 합니다.

- 장점
  - 은닉화, 캡슐화: 변수를 private 하게 사용 할수 있게 해준다. 내부 함수에서만 값을 set, get 을 구현해서 접근할수있다.
- 단점
  - 메모리 누수가 일어날 수 있으므로 초기화 해야된다.

### Http메소드

GET, POST, PUT, PATCH, DELETE, OPTIONS

- ***GET*** 가져오기 파라미터를 이용
- ***POST*** 작성
- ***PUT*** 전체 수정
- ***PATCH*** 부분 수정
- ***DELETE*** 삭제
- ***OPTIONS*** 서버에서 어떤 메소드가 지원하나 알아볼때

### 이벤트 버블링, 캡쳐링, 위임

상위와 하위 엘리먼트 모두 이벤트가 있을때 발생합니다.

- 이벤트 버블링
  - 하위 엘리먼트에서 상위 엘리먼트로 이벤트가 전파되는 특성입니다. stopPropagation으로 막아준다.
- 이벤트 캡쳐링 
  - 상위 엘리먼트에서 하위 엘리먼트로 진행되는 이벤트 전파 방식입니다. 
- 이벤트 위임 
  - 이벤트 위임을 요약해보면 ‘하위 요소에 각각 이벤트를 붙이지 않고 상위 요소에서 하위 요소의 이벤트들을 제어하는 방식’입니다.
  - 각 하위 항목에 이벤트 핸들러를 연결하지 않고, 상위 요소에 하나의 단일 핸들러만 필요하기 때문에 메모리 사용 공간이 줄어듭니다.
  - 제거된 요소에서 핸들러를 해제하고 새 요소에 대해 이벤트를 바인딩할 필요가 없습니다.

### 오버라이딩, 오버로딩 차이?

Overloading(메소드 중복정의)과 Overriding(메소드 재정의)

- 오버로딩
  - 메소드가 처리하는 기능은 같고 메소드 인수의 개수가 다르거나 자료 형(type)이 다른 경우, 메소드의 이름을 동일한 이름으로 부여하여 메소드를 정의 할 수 있는데 이를 메소드 오버로딩(Method Overloading)라 한다. 자바스크립트에는 사실 없는 개념입니다
- 오버라이딩
  - 상위 클래스를 상속 받은 하위 클래스에서 상위 클래스에 정의된 메소드를 재
정의 하는 것으로 객체 지향 프로그램의 특징인 다형성(Polymorphism)을 나타낸다. 재정의
(overriding)는 반드시 상속 관계가 있어야 하며 메소드의 이름, 리턴 타입, 매개 변수의 수나 타
입이 완전히 일치해야 한다. 하지만 자바스크립트는 오버로딩 개념이 없기 때문에 리턴값이 달라도 된다.

### argument와 parameter

Parameter 한글 그대로 번역하면 '매개변수'란 뜻이다. 즉, 함수를 정의 할 때 외부로부터 받아들이는 임의의 값을 의미한다. 아래 함수에서 x,y 가 파라미터.
Argument 우리말로는 '인수' 라고 번역되는데, 함수를 호출할 때 이 때 사용하게 되는 일련의 값들을 아규먼트라고 부른다. 아래 함수에서 3,4가 아규먼트이다.

파라미터의 값으로 아규먼트 3과 4를 대입하였다라고 말하게된다.
``` javascript
    function f(x,y){
    	return x+y;
    };
    
    f(3,4);
```