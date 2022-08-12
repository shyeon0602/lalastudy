# REACT

### 리액트란?

> 메타에서 개발한 유저 인터페이스(UI)를 만들기 위한 오픈 소스 자바스크립트 라이브러리입니다. 이는 새로운 HTML 태그를 만드는 기술입니다.

<br>

### JSX (Javascript XML)

> Javascript에 XML을 추가한 문법 확장입니다. HTML 태그를 변수로 할당하고, 호출하고, 리턴할 수 있는 확장 문법이라고 볼 수 있습니다.<br>

##### XML은 EXtensionable Markup Language로, HTML과 같은 마크업 언어입니다. 이는 데이터를 저장하고 전달하는 것을 목적으로 합니다.

<br>

> 리액트로 프로젝트를 개발할 때 JSX를 사용합니다. 개발자가 JSX를 작성하면 리액트 엔진은 JSX를 기존 자바스크립트로 해석해줍니다.

<br>

- JSX 문법

1.  하나의 요소로 감싸져야 합니다. 즉 반드시 부모 요소 하나로 감싸는 형태여야 합니다.<br>
    이는 Virtual DOM에서 컴포넌트 변화를 감지할 때 효율적으로 비교할 수 있도록 컴포넌트 내부는 하나의 DOM 트리 구조로 이루어져야 하기 때문입니다.<br>
    <!-- 여기서 DOM은 문서 객체 모델로, HTML 문서를 파싱(문장 분석 및 문법적 관계 해석)하여 문서의 구성요소들을 객체로 구조화하여 나타내는 것입니다. HTML Elements, Attributes, CSS styles, Events, Methods 등을 제어할 수 있는 표준 인터페이스를 제공합니다. -->

    여기서 DOM은 문서 객체 모델로, 웹페이지를 이루는 태그들을 자바스크립트가 이용할 수 있게끔 브라우저가 트리구조로 만든 객체 모델을 의미합니다. DOM은 HTML과 스크립팅언어인 Javascript를 이어주는 역할을 합니다.

       <!-- ![DOM TREE](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png) -->

    <p align="center">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png" alt="DOM 트리 구조" width="450" height="500"/>
    </p>

    <br>

    리액트에서는 가상돔을 사용합니다. 가상돔(Virtual DOM)이란 실제 돔에 접근하여 조작하는 대신에 이를 추상화시킨 자바스크립트 객체를 이용해 사용하는 것입니다. 실제 돔은 메모리 누수와 코드량이 많은 문제가 있기 때문에 이를 해결하기 위해 등장했습니다. 즉 가상돔은 무거운 돔의 가벼운 사본 같은 개념입니다.

    자바스크립트는 document라는 전역 객체를 통해 접근할 수 있고, 이를 통해 HTML 태그들을 조종할 수 있습니다.

    - Fragment 태그는 React v16에 추가된 기능으로, 컴포넌트가 여러 엘리먼트를 return할 때 JSX 규칙상 하나의 태그로 묶어야 하는데 Fragment를 사용하면 DOM에 별도의 노드를 추가하지 않고 여러 자식 요소들을 그룹화할 수 있습니다.<br>
      Fragment는 축약형이 존재합니다. <>와 </>로 Fragment 태그를 직접 입력하지 않고도 표현할 수 있습니다.

    <br>

2.  JSX 안에서 자바스크립트 표현식을 사용할 수 있습니다.<br>
    자바스크립트 표현식을 작성하기 위해선 JSX 내부에서 코드를 {}로 감싸주면 됩니다.

<br>

3. if문/for문 대신 삼항 연산자(조건부 연산자)를 사용합니다.<br>
   if 구문과 for 루프는 Javascript 표현식이 아니기 때문에 JSX 내부의 자바스크립트 표현식에서는 사용할 수 없습니다. 즉 return문 내에서 if 구문이나 for 루프를 사용할 수 없다는 것이죠. 그래서 조건부에 따라 다른 렌더링을 할 때 JSX 주변 코드에서 if문을 사용하거나, {} 안에서 삼항 연산자(조건부 연산자)를 사용합니다.<br>

   (1) return문 밖에서 if 구문 사용합니다.<br>
   앞서 말한 것처럼 JSX 내부에서 사용할 수 없기에 return문에서 벗어나 if 구문을 사용할 수 있습니다.

   (2) &&과 ||을 이용할 수 있습니다.<br>
   && 연산자는 거짓을 찾아서 False로 return 합니다. 자바스크립트는 참일 경우, 마지막 참에 원래 값을 return 합니다. 즉 왼쪽값이 참일 경우에만 오른쪽값이 렌더링 됩니다.<br>
   반면 || 연산자는 왼쪽 조건이 거짓일 경우에만 작동하는데

   (3) case문을 사용할 수 있습니다.<br>
   switch case를 활용한 조건부 렌더링도 있습니다.

   (4) 삼항연산자를 사용합니다.<br>
   삼항연산자는 조건식 ? 피연산자1 : 피연산자2 이다. 조건식의 연산결과가 true이면, 결과는 피연산자1이고, 조건식의 연산결과가 false이면 결과는 피연산자2이다. 삼항 연산자는 중첩으로 사용이 가능합니다.
    <!-- if 구문 안의 if 구문, if 구문 안에 또 if 구문을 넣어 사용할 수 있다는 것이죠. -->

<br>

4. React DOM은 HTML attribute 이름 대신 camelCase 프로퍼티 명명 규칙(카멜표기법)을 사용합니다.<br>

   - JSX 스타일링<br>
     : JSX에서 자바스크립트 문법을 쓰려면 {}를 써야 하기 때문에 스타일을 적용할 때에도 객체 형태로 넣어주어야 합니다. 또한 카멜 표기법으로 작성해야 합니다.<br>
     카멜 표기법이란 처음 글자를 소문자로 하는 것과 달리 처음 단어도 대문자로 시작합니다. 예를 들어 font-size로 표기하는 것이 아닌 fontSize로 표기해야 합니다.

   - class 대신 className을 사용합니다. 일반적으로 HTML에서 CSS 클래스를 사용할 때는 class 속성을 사용하지만, JSX에서는 className을 사용합니다.

5. JSX 내에서 주석은 {/\* \*/} 형식으로 사용합니다. 시작 태그를 여러 줄 작성할 때에는 내부에서 //의 형식을 사용할 수 있습니다.

<br>

<!-- - Virtual DOM<br>
  : DOM을 반복적으로 직접 조작하면 그만큼 브라우저가 렌더링을 많이 하게 된다. 또한 그만큼 PC 자원을 많이 소모하게 되는 문제가 발생한다. 이를 해결하기 위해 방법으로 Virtual DOM이라는 DOM을 추상화한 가상의 객체를 메모리에 만들어 놓는 것이다. 변경 사항을 DOM에 직접 수정하는 게 아니라 중간 단계로 Virtual DOM을 수정하고 Virtual DOM을 통해서 DOM을 수정하게 했다. 이는 DOM을 제어하는 API를 직접 호출하지 않고 React 프레임워크를 통해 알아서 Virtual DOM을 제어할 수 있도록 했다.
<br> -->

- 바벨(Babel)<br>
  : 자바스크립트 트랜스파일러인 바벨은 TypeScript나 JSX로 작성된 코드를 JS로 변환해주는 역할을 합니다.<br>
  ##### JS는 명령형 프로그래밍이고, JSX는 선언형 프로그래밍입니다. 선언적 프로그래밍이 더 읽기 쉽고 예측이 쉬워 트랜스파일러를 통해 코드를 변환합니다.

<br>

### 컴포넌트(Component)

> 소프트웨어 시스템에서 재사용이 가능한 각각의 독립된 모듈입니다. 이는 앱을 이루는 최소한의 단위입니다.
> 데이터가 주어졌을 때 이에 맞추어 UI를 만들어주는 기능을 하며, 라이프 사이클 API를 통해 컴포넌트가 화면에서 변화가 있을 때 작업을 수행할 수 있습니다.
> <br>

- UI는 재사용 가능한 개별적인 여러 조각으로 나누고 각 조각을 개별적으로 나누어 코딩합니다.
- Props와 State는 리액트에서 구성요소가 데이터를 받거나 처리하고 보내기 위해 사용됩니다. props 혹은 state 값을 입력 받아 DOM 노드를 생성합니다.<br>
  DOM은 Node의 계층구조로 이루어져 있습니다. Node는 여러가지 DOM 타입들이 상속하는 인터페이스이며 계층적 단위입니다.
  Props는 외부(부모 컴포넌트)에서 상속받는 데이터이고 데이터를 변경할 수 없습니다. 반면 State는 내부(컴포넌트)에서 생성하고 활동하며 데이터를 변경할 수 있습니다.
- 이름은 항상 대문자로 이루어지며 소문자로 시작하는 컴포넌트는 DOM 태그로 취급합니다.

<br>

<!--메서드(method): 클래스의 내부에서 정의된 함수인 멤버 함수(member function)-->

- Component의 선언 방식<br>

  - 클래스형(class): class형 컴포넌트에는 반드시 render()라는 메서드가 있어야 합니다. 이 메서드 내부에서는 JSX를 반환해주어야 하며, props를 읽기 위해서 this.props 키워드를 사용해야 합니다.

  ```jsx
  import React, { Component } from "react";
  class App extends Component {
    render() {
      const name = "리액트";
      return;
      <div>{name}</div>;
    }
  }
  export default App;
  ```

  - 함수형(function): 현재 리액트 메뉴얼에서는 함수형과 Hooks를 사용하는 방식을 권고하고 있습니다.

  ```jsx
  import React from "react";
  function App() {
    const name = "리액트";
    return;
    <div>{name}</div>;
  }
  export default App;
  ```

 <!-- <p align="center">
    <img src="https://velog.velcdn.com/images/gene028/post/f2088f6c-7f2f-4238-b89d-bbe86b2dfa17/image.png" alt="component_선언방식" width="500" height="280"/>
  </p> -->

<br>

- Props<br>
  : 컴포넌트 속성 설정 시에 사용하는 요소로, 프로퍼티(properties)입니다. props의 값은 부모 컴포넌트에서 설정해주며 자식 컴포넌트를 수정하여 렌더링합니다. 컴포넌트의 객체 형태로 전달되며 매개 변수를 통해 조회할 수 있습니다.<br>
  즉 props는 불변의 데이터이며, 부모로부터 전달되어 변경이 불가능합니다.<br>
  props는 class형, function형 모두 사용할 수 있습니다.

<br>

- State<br>
  : 컴포넌트가 가질 수 있는 상태입니다.  
  컴포넌트 내부에서 바꿀 수 있는 값으로, 데이터를 내보낼 때가 아닌 해당 컴포넌트 내부에서 데이터를 전달할 때 사용됩니다.<br>
  props와 달리, 가변 데이터이며 구성 요소에 의해 유지됩니다.
  stat는 함수 내에 선언된 변수처럼 컴포넌트 안에서 관리가 됩니다.
  <br>
  state 객체를 사용하려면 컴포넌트를 생성할 때 가장 상단에 constructor() 함수를 작성하여 컴포넌트를 초기화 합니다. 이는 컴포넌트 생성자에서 super를 호출하기 전까지 this를 사용할 수 없기 때문입니다.

  함수형 컴포넌트는 useState라는 함수를 통해 사용합니다. useState는 배열의 비구조화 할당이 가능합니다. 따라서 배열 안에 들어있는 값을 쉽게 추출할 수 있습니다.

<br>

- component의 분리
  : component는 재사용 가능한 개별적인 여러 조각으로 나눌 수 있습니다.
  react에서 애플리케이션의 크기가 커질수록 하나의 파일에서 코드를 작성하기엔 어려움이 있습니다. 이를 해결하기 위해서 자바스크립트에서는 모듈(module)을 통해 하나의 파일을 여러개의 파일로 나눌 수 있도록 했습니다. 파일 경로를 직접 접근하여 import하는 방법과 폴더 내부에 index.js 파일을 생성하는 방법이 있습니다.

  - export: 변수, 함수, 클래스 앞에 export 키워드를 붙여 모듈의 기능을 외부에서 사용할 수 있도록 내보내는 기능을 합니다.

  ```jsx
  export default Page;
  ```

  - import: export로 내보낸 모듈을 가져오는 기능을 합니다.

  ```jsx
  import { page } from "./Page";
  ```

  <!-- export를 통해 컴포넌트를 내보내주면 됩니다. 함수 앞에 exprot를 사용하거나 함수 끝에 export를 입력해주면 됩니다. 불러오는 과정은 내보내기와 동일하나 export 대신 import를 입력합니다. -->

<!--
  배열(array): 연관된 데이터를 모아서 통으로 관리하기 위해서 사용하는 데이터 타입
  변수가 하나의 데이터를 저장하기 위한 것이라면, 배열은 여러 개의 데이터를 하나의 변수에 저장하기 위한 것이다.

  배열의 생성: []를 사용하여 배열을 만든다. 대괄호 안에 데이터를 콤마로 구분해서 나열하면 배열이 된다.
-->
<br>

- 생명주기 메서드(Lifecycle Method)<br>
  : 컴포넌트(component)의 수명은 페이지에 렌더링 되기 전인 준비과정에서 시작해서 페이지에서 사라질 때 끝납니다. 이는 컴포넌트를 처음으로 렌더링할 때, 컴포넌트를 업데이트하기 전후로 어떤 작업을 처리해야 할 때, 불필요한 업데이트를 방지하기 위해 사용됩니다.
  라이프사이클 메서드는 class 컴포넌트에서만 사용할 수 있습니다.<br>
  라이프사이클 메서드는 어떤 작업을 작동하기 전에 실행하는 will 접두사가 붙은 메서드와 어떤 작업을 작동한 후에 실행하는 did 접두사가 붙은 메서드로 총 9가지 종류를 가집니다.
  <br><br>
  라이프사이클은 mount / update / unmount 3가지 카테고리로 나눌 수 있습니다. <br>

  - mount
    : DOM이 생성되고 웹 브라우저상에 컴포넌트가 나타나는 것입니다.

  - update
    : 컴포넌트가 업데이트 되는 것입니다. <br><br>
    컴포넌트가 업데이트 될 때
    - props가 바뀔 때
    - state가 바뀔 때
    - 부모 컴포넌트가 리렌더링될 때
    - this.foceUpdate로 강제로 렌더링 트리거할 때
      <br><br>
  - unmount
  : 컴포넌트를 DOM에서 제거하는 것입니다.
  <br>
  <p align="center">
      <img src="https://cdn.filestackcontent.com/ApNH7030SAG1wAycdj3H" alt="lifecycle_method" width="500" height="280"/>
  </p>
  <br>

- map() 함수<br>
  : 반복되는 컴포넌트를 렌더링하기 위해 자바스크립트 배열의 내장함수인 map()을 사용할 수 있습니다. 파라미터로 전달된 함수를 사용하여 배열 내 각 요소를 원하는 규칙에 따라 변환한 후 새로운 배열을 생성합니다. 즉 for문처럼 반복문 형태로 사용할 수 있습니다. 컴포넌트를 반복하는 것이죠.<br>

##### 예) 주어진 array의 값을 map을 사용하여 제곱하는 방법

```js
const numbers = [1, 2, 3, 4, 5];
const result = numbers.map((number) => number * number);

console.log(numbers);
//[1, 2, 3, 4, 5]

console.log(result);
//[1, 4, 9, 16, 25]
```

- map() 문법<br>
  : 1. arr.map(callbackFunction, [thisArg])<br> 2. arr.map(callbackFunction(currentValue, index, array), thisArg)<br>

  - callbackFunction: 새로운 배열의 요소를 생성하는 함수, 3가지 인수를 갖습니다.

    1. currentValue: 현재 배열(arr) 내의 값들을 의미, 현재 처리하고 있는 요소<br>
    2. index: 현재 배열 내 값의 인덱스를 의미<br>
    3. array: 현재 처리하고 있는 원본 배열<br>

  - thisArg(선택항목): callback 함수 내부에서 사용할 this 레퍼런스를 설정합니다.

<!-- - map() 사용하는 방법<br>
  <!-- : callbackfn을 통해 주어진 3개의 인자(요소값, index, 순회하는 대상 객체)를 사용해 새로운 값을 만드는 함수를 등록합니다. -->

<br>

- key<br>
  : 요소의 리스트를 만들 때, react가 어떤 아이템이 바뀌었는지, 추가되었는지, 삭제되었는지를 인식하는데 사용됩니다.
  react 내에서는 모든 컴포넌트가 동일한 이름을 가졌더라도 유일한 존재여야 하기 때문입니다.<br>
  key는 고유한 값이어야 하기 때문에 배열 요소의 id를 사용하거나 index로 사용합니다.
  그러나 index는 배열의 순서가 바뀌면 index도 바뀌기 때문에 id를 사용하는 것을 권장합니다.

<br>

### 리액트 Hooks

> Hook은 react 16.8 버전에 추가된 공식 라이브러리로, class형 컴포넌트에서만 사용할 수 있었던 state와 lifecycle을 함수형 컴포넌트에서도 사용할 수 있도록 해줍니다.
> Hook을 이용하여 기존 class 바탕의 코드를 작성할 필요없이 상태 값과 여러 react 기능을 사용할 수 있습니다. 이에 따라 class형 컴포넌트에서만 가능하던 상태관리를 더 쉽게 할 수 있게 되었습니다.

##### 함수형 컴포넌트는 기본적으로 리렌더링 될 때 함수 안에 작성된 모든 코드가 다시 실행됩니다.

##### 한편 class형 컴포넌트들은 method의 개념이기 때문에, 리렌더링 되더라도 rende()를 제외한 나머지 method와 state는 그대로 보존이 되어 있습니다.

- useState<br>
  : 'use'로 시작하는 useState 훅은 메타(페이스북)이 제공하는 내장된 훅입니다. 이는 배열을 리턴하는 역할을 합니다.

  1. react에서 useState를 import 받아야 합니다.<br>
     react Hooks의 useState는 컴포넌트의 state를 간편하게 생성하고 업데이트 시킬 수 있게 해주는 도구를 제공합니다.
     ```jsx
     import { useState } from "react";
     ```
  2. 변수를 선언해줍니다.<br>

     ```jsx
     const [state, setState] = useState(초기값);
     ```

     state 생성과 동시에 가져야 하는 초기값을 useState()의 인자로 넣어주면 state와 setState라는 두가지 요소를 배열 형태로 리턴해줍니다. 여기서 변수명은 꼭 state가 아니어도 됩니다.<br>

  ##### const: 상수(constant)를 의미합니다. const 키워드로 선언하면 변치 않는 값을 갖는 변수를 생성합니다. 또한 const로 선언한 변수는 값을 재할당할 수 없습니다.

  3. state 값을 변경하려면 setState()를 불러서 인자에 변경될 값을 넣어주는 변수 재선언을 해줍니다.

     ```jsx
     setState(1);
     ```

     setState()를 이용해서 state의 값을 변경하면 해당 컴포넌트는 화면에서 다시 렌더링 되어 state가 변경될 때마다 화면이 업데이트 됩니다.

- useEffect()
  : 리액트 컴포넌트가 렌더링 될 때마다 특정 작업을 실행할 수 있도록 하는 hook입니다. useEffect는 컴포넌트가 mount/unmount/update 됐을 때 특정 작업을 처리할 수 있습니다. 이는 클래스형 컴포넌트에서 사용할 수 있었던 생명주기 메소드를 함수형 컴포넌트에서도 사용할 수 있게 된 것입니다.<br>

  useEffect(function, deps) 형태로 구성되어 있습니다. function은 수행하고자 하는 작업이고, deps는 배열의 형태입니다. 배열 안에는 검사하고자 하는 특정 값 또는 빈 배열이 들어갑니다.<br>

  ```jsx
  import React, { useEffect } from "react";
  useEffect(() => {
    console.log("mount될 때 실행");
  }, []);
  ```

  이렇게 deps 위치에 빈 배열을 넣으면 컴포넌트가 화면에 처음 렌더링 될 때 한번만 실행합니다.

- useNavigate() <br>
  : 페이지 이동을 할 수 있도록 하는 hook입니다. useNavigate 훅을 실행하면 페이지 이동을 할 수 있게 해주는 함수를 반환합니다. 반환하는 함수를 navigate라는 변수에 저장 후 navigate의 인자로 설정한 path 값을 넘겨주면 해당 경로로 이동할 수 있습니다.

  ```jsx
  import { useNavigate } from "react-router-dom";

  function Login() {
    const navigate = useNavigate();

    const goToMain = () => {
      navigate("/main"); // 메인페이지로 이동할 수 있도록 함
    };

    return (
      <div>
        <!-- 로그인 버튼을 누르면 메인페이지로 이동 -->
        <button onClick={goToMain}>로그인</button>
      </div>
    );
  }
  ```

  <br>

- useParams() <br>
  : 라우터 사용 시 파라미터 정보를 가져와 활용할 때 사용하는 hook입니다.

  ```jsx
  import { useParams } from "react-router-dom";

  const test = () => {
    let { params } = useParmas();

    return (
      <div>
        <p>현재 페이지의 파라미터는 {params} 입니다.</p>
      </div>
    );
  };
  ```

- useLocation() <br>
  : 사용자가 현재 머물러있는 페이지에 대한 정보를 알려주는 hook입니다. 객체 형식으로 보여주기 때문에 location.state로 접근할 수 있습니다.

  ```jsx
  import { useLocation } from "react-router-dom";

  function Order() {
    const location = useLocation();

    const { result } = location.state;
  }
  ```

  <!-- hooks 추가 공부 필요 -->

<br>

### 리액트 라우터(React Router)

라우터를 사용하기 위해서 라이브러리를 설치합니다.

```
npm install react-router-dom
```

<!-- - MPA

- SPA -->

- 라우팅
  : 다른 주소에 다른 화면을 보여주는 것을 라우팅이라고 합니다.

##### 라우터와 라우팅은 다릅니다. 라우터는 라우트를 이동시키는 컨트롤 도구입니다. 여기서 라우트는 각각의 화면이나 url입니다. 즉 라우트는 요소이고, 라우터는 도구입니다.

- Route 사용법

```jsx
<Route path="주소규칙" element="{보여줄_컴포넌트}" />
```

##### 예시)

```jsx
<Route path="/post/:postID" element={<ShowPost></ShowPost>}></Route>
```

- 페이지 주소 정의
  - url 파라미터: 특정 아이디, 이름을 사용하여 조회할 때 사용합니다.
  ```jsx
  <Link to="/movies/1" />
  ```
  - 쿼리스트링: 키워드 검색, 페이지네이션, 옵션을 전달할 때 주로 사용합니다.
    useState를 통해 search가 가능합니다. 또한 url 파라미터와 달리 Route 컴포넌트를 별도로 설정하지 않아도 됩니다.
  ```jsx
  <Link to="/movies/1?detail=true" />
  ```
  <br>
- Link 컴포넌트 <br>
  : Link는 a 태그처럼 링크를 연결해줍니다.(url과는 다른 path 개념) <br>
  리액트 라우터에서 페이지를 이동할 때는 Link 컴포넌트를 사용하면 이동하고자 하는 경로(url)로 이동할 수 있습니다.

  ```jsx
  <Link to="/movie">movie</Link>
  ```

##### Link의 경로와 route의 path 경로는 동일해야 합니다.

##### Link 컴포넌트를 사용하면 브라우저의 주소만 바꾸며 페이지를 새로 불러오진 않습니다.

<br>

- NavLink 컴포넌트 <br>
  : 특정 링크에 스타일을 넣을 수 있습니다. activeStyle과 activeClassName 속성을 사용하여 react 웹의 현재 url과 to의 링크가 일치할 때 activeStyle과 activeClassName이 활성화되고, 일치하지 않으면 비활성화가 됩니다.

<!-- - navigate 컴포넌트 <br>
  : 특정 행동을 했을 때 해당 주소로 이동해줄 수 있도록 만들어줍니다. -->
