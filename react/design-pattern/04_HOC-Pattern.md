# HOC-Pattern

## 정리 & 요약

- HOC(Higher-Order-Components) pattern은 컴포넌트를 받아 새로운 컴포넌트를 반환하는 함수이다.

- HOC 패턴은 일부 리액트 훅으로 대체가 가능하지만 완전히 대체 가능은 아니다. 따라서 아직까진 유효한 패턴이다.

- 다수의 HOC 컴포넌트를 합성하여 사용할 수 있다.

- HOC가 적합한 케이스
  - 같지만 커스터마이징이 필요없는 동작이 많은 컴포넌트에 있을 떄
  - 컴포넌트가 커스텀 로직없이 혼자 동작 가능할 때

## 장점

### 재사용성

### 버그의 위험성 감소

### 관심사 분리, 한곳에 로직을 몰아놓음으로써 `DRY` 유지가능

## Reference

- [Patterns.dev](https://www.patterns.dev/react/hoc-pattern/) - 디자인 패턴-compound pattern(react, js, vue)
