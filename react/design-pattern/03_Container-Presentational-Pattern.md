## 정리 & 요약

- Container-Presentational Pattern은 어플리케이션 로직으로부터 뷰를 분리 하는 데 사용 할 수 있다.

- Presentational Components : `어떻게` 유저에게 데이터가 보여야 할 지를 다룬다. props로 데이터를 받아 화면에 보여주는 역할을 한다. 즉 UI(view)만을 다루는 컴포넌트이다. 일반적으로 UI를 위한 목적이 아닌 이상 이 컴포넌트는 `stateless`하다. 즉 상태를 포함하지 않는다.

- Container Components : `무슨` 데이터를 유저에게 보여야 할 지를 다룬다. 이 컴포넌트는 데이터에 대해 다룬다. 즉 외부 API에서 데이터를 fetch하고 Presentaitonal Components에 넘겨주는 역할이다. 이 컴포넌트에서는 아무것도 렌더링(화면에 무언가를 그리지) 하지 않는다.

- 단 이 패턴은 대부분의 경우 훅으로 대체가 가능하다. 관련 글을 좀 읽어보니 이 패턴은 훅이 나오기 전에 흔하게 사용되었던 패턴이라고 한다. 클래스형 컴포넌트에서 많이 사용된 패턴 같다.

## 장점

### 관심사의 분리

UI만을 담당하는 컴포넌트와 상태와 데이터를 다루는 컴포넌트가 분리된다.

### 재사용성

### 테스트가 용이

Presentational Components는 일반적으로 순수(Pure)하기 때문에 우리가 전달한 데이터를 기반으로 어떻게 컴포넌트가 렌더 될 지 알 수 있다.

## Reference

- [Patterns.dev](https://www.patterns.dev/react/presentational-container-pattern) - 디자인 패턴-compound pattern(react, js, vue)
