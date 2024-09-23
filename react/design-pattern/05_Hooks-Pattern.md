# Hooks-Pattern

## 정리 & 요약

- React 16.8 이후 Hooks가 소개 되었다. 훅들은 상태와 라이프 사이클을 클래스형 컴포넌트 없이 사용가능하게 만들었다.
- 컴포넌트 사이에 코드를 공유하는 방법은 HOC 또는 렌더 프롭스패턴을 많이 사용한다. 하지만 이런 패턴들은 `wrapper hell`을 만들 가능성이 있다. `wrapper hell`은 데이터흐름을 이해하기 어렵게 만든다.
- 또한 로직을 추가해 나아갈수록 로직들이 얽히기에 로직 동작에 대한 예측이 어렵다.
- 이런 문제를 훅으로 일부 해결이 가능하다. 또한 자신의 입맛대로 커스텀 훅을 만들 수도 있다. 단 훅의 규칙(Rules of Hooks)을 지켜야 한다.

## 장점

### 코드의 줄(양)이 줄어든다.

### 복잡한 컴포넌트를 간단히 만든다.

JS의 클래스는 다루기 어렵다. 리액트 훅을 활용하면 훨씬 간편하고 쉽게 개발이 가능하다.

### non-visual logic 공유

훅이 나오기 전까지 리액트에서는 non-visual logic을 공유하고 추출(분리)할 방법이 마땅히 없었다. 훅이 출시 이후 이 문제를 해결가능했다.

## Reference

- [Patterns.dev](https://www.patterns.dev/react/hooks-pattern) - 디자인 패턴-compound pattern(react, js, vue)
