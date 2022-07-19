# REACT

### 리액트란?

> 메타에서 개발한 유저 인터페이스(UI)를 만들기 위한 오픈 소스 자바스크립트 라이브러리입니다. 이는 새로운 HTML 태그를 만드는 기술입니다.

<br>

### JSX(Javascript XML)

> Javascript에 XML을 추가한 문법 확장입니다. HTML 태그를 변수로 할당하고, 호출하고, 리턴할 수 있는 확장 문법이라고 볼 수 있습니다.<br>
> 리액트로 프로젝트를 개발할 때 JSX를 사용합니다. 개발자가 JSX를 작성하면 리액트 엔진은 JSX를 기존 자바스크립트로 해석해줍니다.

<br>

- JSX 문법

1.  하나의 요소로 감싸져야 합니다. 즉 반드시 부모 요소 하나로 감싸는 형태여야 합니다.<br>
    이는 Virtual DOM에서 컴포넌트 변화를 감지할 때 효율적으로 비교할 수 있도록 컴포넌트 내부는 하나의 DOM 트리 구조로 이루어져야 하기 때문입니다.<br>
    여기서 DOM은 문서 객체 모델로, HTML 문서를 파싱(문장 분석 및 문법적 관계 해석)하여 문서의 구성요소들을 객체로 구조화하여 나타내는 것입니다. HTML Elements, Attributes, CSS styles, Events, Methods 등을 제어할 수 있는 표준 인터페이스를 제공합니다.

       <!-- ![DOM TREE](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png) -->

    <p align="center">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/DOM-model.svg/1200px-DOM-model.svg.png" alt="DOM 트리 구조" width="450" height="500"/>
    </p>

    <br>

2.  JSX 안에서 자바스크립트 표현식을 사용할 수 있습니다.<br>
    자바스크립트 표현식을 작성하기 위해선 JSX 내부에서 코드를 {}로 감싸주면 됩니다.

<br>

3. if문/for문 대신 삼항 연산자(조건부 연산자)를 사용합니다.<br>
   if 구문과 for 루프는 Javascript 표현식이 아니기 때문에 JSX 내부의 자바스크립트 표현식에서는 사용할 수 없습니다. 그래서 조건부에 따라 다른 렌더링을 할 때 JSX 주변 코드에서 if문을 사용하거나, {} 안에서 삼항 연산자(조건부 연산자)를 사용합니다.

<br>

4. React DOM은 HTML attribute 이름 대신 camelCase 프로퍼티 명명 규칙을 사용합니다.<br>

   1. JSX 스타일링<br>
      : JSX에서 자바스크립트 문법을 쓰려면 {}를 써야 하기 때문에 스타일을 적용할 때에도 객체 형태로 넣어주어야 합니다. 또한 카멜 표기법으로 작성해야 합니다.<br>
      카멜 표기법이란 처음 글자를 소문자로 하는 것과 달리 처음 단어도 대문자로 시작합니다. 예를 들어 font-size로 표기하는 것이 아닌 fontSize로 표기해야 합니다.

   2. class 대신 className을 사용합니다. 일반적으로 HTML에서 CSS 클래스를 사용할 때는 class 속성을 사용하지만, JSX에서는 className을 사용합니다.

5. JSX 내에서 주석은 {/\* \*/} 형식으로 사용합니다. 시작 태그를 여러 줄 작성할 때에는 내부에서 //의 형식을 사용할 수 있습니다.

<br>

- 바벨(Babel)<br>
  :
