# Compound-Components-Pattern

## 정리 & 요약

- 이 패턴은 하나의 일(task)를 하기 위해 함꼐 동작하는 컴포넌트들을 만들기 위해 사용되는 패턴이다. 예를 들어 select와 option을 생각해보면 된다. option은 select에 의존(depend on)한다. 이와 같이 만들어진 컴포넌트들은 상태(state)와 로직(logic)을 공유하며 서로 의존하게 된다.
- 상태와 로직은 `ContextAPI`를 이용해서 공유된다.
- 최상단 부모 컴포넌트는 상태와 로직을 하위 자식 컴포넌트에 전달하는 역할을하고 자식 컴포넌트들은 그 상태와 로직을 받아 동작하게 된다.
- 자식 컴포넌트를 부모 컴포넌트의 프로퍼티로 만듦으로써 다른 파일에서 이 컴포넌트를 사용하게 되면 최상위 컴포넌트를 Import하여 사용하게 된다.

## 장점

### props drilling 문제 완화

A -> B -> C 컴포넌트 관계과 이렇게 되어있다고 가정해보자. 이럴 경우 C에서 필요한 데이터나 로직이 A에 정의 되어있을 경우 props로 B를 거쳐 C로 전달하게 된다. B는 중간 다리역할만 할 뿐 이다. 이 문제는 컴포넌트 관계가 깊어질수록 심해진다. 이것을 props drilling이라고 하는데 ContextAPI를 사용함으로써 이 문제를 일부 해결 했다.

### 재사용성

한번 컴포넌트를 설계하면 기존 컴포넌트를 복사할 필요 없이 최상위 부모 컴포넌트만 import하여 사용하면 된다. 이로써 전체적인 코드량과 복잡성이 줄어들어 향후 유지보수, 업데이트에 큰 이점을 지니게 된다.

### 관심사의 분리

각각의 컴포넌트는 각각의 책임(UI, Logic)을 갖는다. 이로써 단일책임원칙(Single Responsibility Principle)을 지키게 되고 유지보수 측면에 이점을 갖게 된다.

## Reference

- [Patterns.dev](https://www.patterns.dev/react/compound-pattern) - 디자인 패턴-compound pattern(react, js, vue)
- [React Design Patterns: Compound Component Pattern](https://medium.com/@vitorbritto/react-design-patterns-compound-component-pattern-ec247f491294)
