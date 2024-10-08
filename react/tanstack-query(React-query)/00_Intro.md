# Tanstack-Query

## Tanstakc-Query를 공부하게 된 이유

리액트 프로젝트를 하면서 데이터 패칭을 할 때 useEffect를 이용하였다. 처음에는 이것또한 쉽지 않았지만 어느정도 익숙해진 후 다시 돌아보니 여러 문제점이 보였다.  
우선 비슷한 코드들이 반복적으로 발생한다는 점이었다. useEffect안에 fetch혹은 axios를 이용하여 데이터 패칭을 하는 것은 동일하기에 엔드포인트들만 조금씩 다를 뿐 거의 코드는 같은 경우가 많았다. 이로 인해 코드가 더러워지는 문제가 발생했다. 두 번째는 캐싱 문제였다. A라는 페이지에서 데이터를 패칭 받고 B로 넘어갔다 다시 돌아오면 데이터 패칭이 다시 이루어졌다. 사용자 경험 측면에서도 좋지 않다고 생각되고 계속 요청을 보내는 거니 서버비용문제, 부담문제가 클 것 같았다. 이 문제를 해결하기 위해 tanstack-query를 공부를 하게 되었다.

## useEffect를 이용한 데이터 패칭의 문제점

리액트 공식문서에서는 useEffect를 이용해서 데이터 패칭을 하는데 문제점이 있다고 지적하고 라이브러리나 프레임워크를 사용한다면 프레임워크에서 지원해주는 기능을 사용하라고 권장하고 있다.
문제점은 아래와 같다.

### 기본적으로 서버에서 실행이 되지 않는다.

Effects는 서버에서 실행되지 않으니 초기 상태는 데이터가 없게 된다. 클라이언트에서 모든 JS파일을 다운 받고 앱이 렌더 된 이후 패칭이 시작된다. 이것은 비효율적이라고 지적하고 있다.

### `network waterfalls`를 만들기 쉽다.

부모 컴포넌트를 렌더링 하고 거기서 데이터를 패칭하고 자식 컴포넌트를 랜더링하고 그리고 다시 자식 컴포넌트들이 데이터 패칭을 시작하게 된다. 이런 식으로 렌더링과 데이터패칭이 이루어질 경우 네트워크 요청이 느린 상태로 진행된다면 병렬로 모든 데이터를 처리하는 것보다 훨씬 느리게 된다.

### `preload`와 `caching` 미지원

여기서 앞서 느낀 문제점이 등장한다. 컴포넌트가 언마운트(unmount)된 이후 다시 마운트(mount)가 된다면 다시 데이터 패칭을 진행하게 된다.

### `boilerplate code`양산

역시 앞서 느낀 문제점이다. 비슷한 코드들이 반복적으로 등장하게 되는 문제가 발생한다. 이런 문제는 일부 `custom hook`을 활용하여 문제를 해결 할 수 있었다. 하지만 위에 캐싱문제는 해결하지 못했다.

## useEffect 문제 해결 방법

위에 같은 문제로 리액트에서는 두가지 해결책을 제시한다.  
첫 번째로 next, remix, gatsby 같은 프레임워크를 사용한다면 거기에서 제공해주는 기능들을 활용하여 이 문제를 해결하라고 한다.
두 번째는 라이브러리 사용이다. `tanstack-query(react-query)`, SWR, React-Router, RTK-Query 등을 사용하여 캐싱문제를 해결해보기 고려하라고 한다. 아니면 useEffect 사용시 직접 로직을 만들어 추가적으로 더해 사용하라고한다. 하지만 굳이 라이브러리를 만들어 놨는데 이리 먼 길을 돌아갈 필요가 있나 싶다.

## 왜 Tanstack-Query 인가?

npm-trends(과거 1년 다운로드 수 기준)을 보면 이미 Tanstack-query의 다운로드가 SWR을 넘었다. 대세는 swr보다 tanstack-query인 듯 싶다. swr은 실제로 사용해보진 않았지만 vercel에서 만들었으니 같은 출신 next와 궁합이 좋을 것 같다는 추측아닌 추측을 해본다. rtk-query는 이미 프로젝트에 redux(rtk)를 도입한 프로젝트에 사용하면 좋을 것 같다.

## Tanstack-Query 란?

tanstack-query 공식문서에서 소개하길

> TanStack Query (FKA React Query) is often described as the missing data-fetching library for web applications, but in more technical terms, it makes fetching, caching, synchronizing and updating server state in your web applications a breeze.

`서버 상태`를 업데이트하고 동기화하고 캐싱, 패칭하기 쉽게 해주는 라이브러리이다고 보는 것이 기술적 용어면에서 더 가깝다고 한다.

## Server State(서버 상태)란?

서버 상태는 말 그대로 서버에있는 데이터 혹은 Api로 fetched 된 데이터를 말한다.

## 정리 & 요약

useEffect로 데이터 패칭을 시도 하는 것은 잘못된 게 아니다. 하지만 여러 문제점이 존재한다. 이 문제점을 해결하기 위한 라이브러리 중 하나이면서 가장 많은 다운로드 수를 갖고 있는 것이 tanstack-query이다. tanstack-query는 서버 상태를 다루기 위한 라이브러리이다.

## Reference

[React공식문서](https://react.dev/reference/react/useEffect#fetching-data-with-effects) - fetching data with effects  
[Tanstack-Query공식문서](https://tanstack.com/query/latest/docs/framework/react/overview#motivation) - Overview
