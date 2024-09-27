# Important Defaults

## retried 3 times

에러를 보여보여주기 전 리액트 쿼리는 3번의 시도를 한다. retry, retryDelay옵션을 통해 횟수와 딜레이 시간을 바꿀 수 있다.

## gcTime

기본적으로 inactive된 쿼리들은 5분뒤 가비지값으로 변환된다. `gcTime`으로 가비지로 수집되는 시간을 조절한다.

## staleTime

쿼리 인스턴스들은 기본적으로 캐시된 데이터 상태가 `stale`하다고 여겨진다. `staleTime`옵션을통해 이를 조절 할 수 있다.
여기서 stale은 구데이터 즉 업데이트가 된 새로운 데이터가 아닌 그 이전 데이터를 말하는 것 같다. 예를 들어 유저1과 유저2가 동시에 같은 posts를 패칭 받았다고 가정하자. 유저2가 새로운 데이터를 생성했다면 기존 유저1은 stale한 데이터를 가지고 있는 상태이다.

stale 쿼리들은 자동적으로 background에서 아래와 같은때 리패칭된다.

- 새로운 인스턴스가 마운트될 떄
- 윈도우(브라우저창)이 다시 리포커스 될 때
- 네트워크가 다시 연결될 때
- 설정된 리패칭 시간이 되었을 때

## Refrence

[Tanstack-Query공식문서](https://tanstack.com/query/latest/docs/framework/react/guides/important-defaults) - Important Defaults
