# GraphQL_base
#### 장점
1. over-fetching을 막아준다 -> 필요한 데이터를 요청한다. -> 내가 요청한것 데이터만 받을수 잇다 : rest api는 필요하지 않는 데이터도 받을수 밖에 없는데 그런 점과는 다름
2.Underfetching: 필요한 데이터를 위해 여러개의 리퀘스트를 날려아하는 rest api 문제점을 단하나의 싱글 리퀘스트로 거기서 필요한 데이터를 다 받을수 잇다

### 사용법
```
 {
  받구 싶은 데이터의 파라미터 {
  
  }
 }
```
### 클라이언트 graphQL 사용하기 
```
npm i @apollo/client graphql
npm i react-router-dom@6
```

- Apollo Client는 GrpahQL API를 호출하기 위해 사용되는 라이브러리입니다. 
- 이번 포스팅에서는 React 앱에서 Apollo Client를 사용하여 GraphQL API를 호출하는 방법에 대해서 알아보겠습니다.

```react
import {ApolloClient, InMemoryCache} from "apollo-boost";

const client = new ApolloClient({
  uri: "https://countries.trevorblades.com", // 그래프큐앨이 돌아가는 url
  cache:ner InMemoryCache()
});

// 위에 기재한 url에 아래의 쿼리를 보냄  =? 데이터 패치하는 역함 ????
client.query({
    query: gq;`
    {
    alalMobies{
    title}
    }`
})
export default client
```

// https://www.daleseo.com/graphql-react-apollo-client/ 참고하
-.app 을 ApolloProvider 로 감싸다. => 컴포넌트에서 useApolloClient 로 접근 가능
- 위에 방법을 더 줄여주기 위해서 useQuery hook 사용

#### useQuery (apllot/client): 선언형 코드
```
const ALL_MOVIES = gql`

    // query getMovies은 생략 가능 함수명은 개발자 임의로 작성
    query getMovies {
        alalMobies{
            title
        }
    }
`
export defult Movies(){
// 이런 식으로 사용 가능
const {data, loading, error} = useQuery(ALL_MOVIES)

}

```