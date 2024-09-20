# Render Props

## 정리 & 요약

- Render Props는 React 컴포넌트 간에 코드를 공유하기 위해 함수를 props를 이용하는 간단한 테크닉이다. 즉 JSX를 리턴하는 함수를 props로 전달하는 방식이다.

- 이 패턴은 자체적으로 렌더링 로직을 구현하는 대신, react elements를 반환하고 호출하는 함수를 사용한다.

## 장점

### 로직과 데이터 공유 문제 해결

render props 패턴을 사용시 컴포넌트 간 데이터, 로직 공유가 쉬워진다.

### 재사용성

### HOC 패턴이 직면한 문제 일부 해결

HOC 패턴을 사용하면서 생기는 문제들 중 naming collisions 문제가 render props 패턴에서는 더 이상 발생하지 않는다.  
render props는 명시적(분명하게)으로 props를 전달하므로 HOC 패턴에서 발생하는 암묵적(불분명) props 문제를 해결했다.

### 렌더링 컴포넌트(UI)와 로직 분리 가능

## Reference

- [Patterns.dev](https://www.patterns.dev/react/render-props-pattern/) - 디자인 패턴-compound pattern(react, js, vue)
- [Render Props](https://ko.legacy.reactjs.org/docs/render-props.html) - React 공식문서(한글)
