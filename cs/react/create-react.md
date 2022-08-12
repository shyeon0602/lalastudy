# React-app 만들기

1. app 생성

```
npx create-react-app 파일이름
cd 파일이름
yarn start
```

2. 라우터 설치

```
yarn add react-router-dom
```

BrowserRouter - history API를 사용해 URL과 UI를 동기화하는 라우터입니다.
Route - 컴포넌트의 속성에 설정된 URL과 현재 경로가 일치하면 해당하는 컴포넌트, 함수를 렌더링한다.
Link - 'a'태그와 비슷합니다. to속성에 설정된 링크로 이동합니다. 기록이 history스택에 저장됩니다.
Switch - 자식 컴포넌트 Route또는 Redirect중 매치되는 첫 번째 요소를 렌더링합니다. Switch를 사용하면 BrowserRouter만 사용할 때와 다르게 하나의 매칭되는 요소만 렌더링한다는 점을 보장해줍니다.사용하지 않을 경우 매칭되는 모두를 렌더링합니다.<br>
출처: https://data05.tistory.com/233?category=1019899 [K-CodingStory:티스토리]

3. defaultProps 잡기

```jsx
Login.defaultProps = {
  user_info: {
    user_name: "mean0",
  },
};
```

4. 스타일 패키지 설치

```
yarn add styled-components
```

5. grid 잡기
   기획서에서 잡은 동일한 여백을 처음에 잡아주는 것이 좋습니다.

> props를 통해 데이터를 가져오는 방법 알아두기!

```jsx
${(props) => props.[데이터]};
```
