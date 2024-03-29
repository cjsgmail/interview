# 리액트

> ### React를 사용하는 이유

- Virtual DOM의 존재
- React Native의 앱 개발 가능
- Component를 사용한 재사용이 가능하고 유지보수의 용이함

> ### SPA(Single Page Application)란?

- 서버로부터 새로운 페이지를 불러오지 않고 현재의 페이지를 동적으로 다시 작성함으로써 사용자와 소통하는 웹 애플리케이션이나 웹사이트를 말합니다.
- 즉, 현재의 HTML을 고정하고 변경되는 부분에 대해서만 서버에서 불러와 클라이언트 사이드에서 렌더링하는 방식인 것입니다.

> ### SPA의 장점

- 페이지 로딩속도가 빠릅니다.

  - 클라이언트가 최초 요청에 서버로부터 모든 재료(html, css, js 등)를 가져오기 때문에 사용자의 요청에 대해 클라이언트 사이드에서 렌더링하기 때문에 서버로부터 데이터를 매번 가져올 필요가 없어 페이지 이동 간에 딜레이가 거의 없습니다.

- 사용자 경험이 우수합니다.
  - 빠른 로딩속도는 사용자 경험을 증대시키고 사용자가 웹사이트에 머무는 데 있어 로딩으로 인한 피로도도 적을 것입니다.

> ### SPA의 단점

- 최초 페이지 로딩속도가 느립니다.

  - 클라이언트가 최초로 서버에 요청할 때 모든 데이터를 가져오기 때문에 상대적으로 최초 요청에서 속도가 MPA에 비해 상대적으로 느립니다.

- SEO에 적합하지 않을 수 있습니다.

> ### 모든 사이트를 SPA로 구현해야하는가?

- 예를 들어, EC(E-Commerce) 사이트의 경우 방대한 양의 콘텐츠를 담아야하기 때문에 한번에 모든 요소를 요청하는 SPA 방식보다는 MPA방식으로 구성하는 것이 SEO뿐만 아니라 페이지 속도 측면에서도 더 유리하다고 볼 수 있습니다.

- 사이트의 콘텐츠가 적고 화려하면서 부드러운 이미지 구현이 필요한 사이트의 경우 SPA가 적합할 수 있습니다. 또한 모바일 환경에서 사용자 경험이 좋은 SPA방식은 SEO에 완전하지 않거나 불편한 보완책을 감수하고 SPA를 선택할 수 있습니다.

> ### React의 생명주기에 대해서 설명해주세요

- 함수형 리액트에서는 useEffect를 통해 컴포넌트의 마운트, 업데이트, 언마운트를 관리할 수 있습니다.
- useEffect는 컴포넌트 안에서 state와 props에 접근이 가능하고 기본적으로 첫 번째 렌더링과 그 이후의 모든 업데이트에서 사용됩니다.
- 모든 effect는 정리를 위한 클린업 함수를 반환할 수 있는데 이는 컴포넌트가 언마운트될 때 실행됩니다.

> ### DOM과 Virtual DOM의 차이

- DOM은 Document Object Model로 HTML 코드로 설계된 웹페이지가 브라우저 안에서 화면에 나타나고, 이벤트에 반응하며, 값을 입력받는 등 기능들을 수행할 객체들로 실체화된 형태를 의미합니다.
- Virtual DOM은 실제 DOM을 모방하는 형태로 메모리 상에서만 존재하는 가상의 DOM을 의미합니다.
- 변화가 실제 DOM에 적용되기 전 가상의 DOM을 한번 거쳐 미리 처리하고 저장한 후 실제 DOM에 업데이트 할 수 있게 해줍니다.
- 최근에는 Single Page Application을 많이 사용하면서 DOM tree를 즉각적으로 변경할 일이 생겼습니다.
- 전체 페이지를 서버에서 매번 보내주는 것이 아니라, 브라우저 단에서 자바스크립트가 관리하기 때문에, DOM조작을 더욱 더 효율적으로 할 수 있게 최적화가 필요하게 되었고 그래서 가상 돔이 등장하게 되었습니다.

> ### 그렇다면 가상 DOM이 항상 효율적인가요?

- 사용자와 상호작용이 많은 웹에서는 더 효율적이지만 단순 정보제공만 하는 웹에선 일반 Dom이 더 효율적일 수 있습니다.

> ### React에서 setState로 state를 변경시키는 이유에 대해서 설명해주세요.

- 직접 값을 바꾸게 되면 리렌더링이 되지않고 setState를 통해서 바꾸는 것만 리렌더링이 되기 때문에 setState를 사용해서 state를 변경해야 합니다.

> ### React에서 컴포넌트가 리렌더링을 하는 조건

- 자신의 state가 변경될 때
- 부모 컴포넌트로부터 전달받은 props가 변경될 때
- 부모 컴포넌트가 리렌더링 될 때

> ### Props에 대해서

- 컴포넌트의 속성을 의미한다.
- 성별이나 이름처럼 변하지 않는 외부로부터 전달받은 값이다.
- 부모 컴포넌트로부터 전달받은 값이다.
- 객체의 형태이다.
- 읽기 전용이다.

> ### State에 대해서

- 컴포넌트 내부에서 변할 수 있는 값

> ### useRef에 대해서

- React 애플리케이션을 만들 때 DOM을 직접 조작하는 것은 지양해야한다.
- 개발을 하다보면 DOM을 직접 건드려야하는 상황이 발생하기도한다. 이럴 때 사용할 수 있는 것이 바로 useRef 라는 Hook 함수
- focus
- text selection
- media playback
- 애니메이션 적용
- d3.js, greensock 등 DOM 기반 라이브러리 활용

> ### useMemo와 useCallback을 사용하는 이유

- 너무 잦은 리렌더링은 앱의 성능에 좋지 않은 영향을 끼칩니다.
- 렌더링을 최적화 해주는 훅이 useMemo와 useCallback입니다.
- useMemo는 값의 재사용을 위해 사용하고 useCallback은 함수의 재사용을 위해 사용합니다.
- 공식 문서에서는 우선 useMemo나 useCallback을 사용하지 말고 동작할 수 있는 코드를 만들어보라고 권합니다.
- 일단 만들어본 후에 리팩토링을 할 때 어느 부분이 많은 비용이 들어가고 어느 부분이 동작하지 않아도 되는 부분인지를 확인 한 다음에 useMemo나 useCallback을 이용해서 관리를 해보는 것이 좋습니다.

> ### 커스텀 Hook을 사용하는 이유

- 중복된 로직을 재활용 가능하다는게 가장 큰 장점 입니다.
- useFocus를 만들어서 인풋에 포커징되는 훅과 useScroll이라는 훅을 만들어 페이지 이동을 했을 떄 최상단으로 고정되는 훅을 만들어 본 적이 있습니다.

> ### 전역 상태관리를 사용하는 이유에 대해서 설명해주세요

- 리액트에서 데이터는 부모에서 자식컴포넌트로 단방향의 흐름을 가지기 때문에 전역 상태관리를 사용하지 않으면 상태 끌어올리기, Props 내려주기를 여러 번 거쳐야 합니다.
- 해당 상태를 직접 사용하지 않는 컴포넌트들도 상태 데이터를 가지기 때문에 애플리케이션이 복잡해질수록 데이터 흐름도 복잡해집니다.
- 컴포넌트 구조가 바뀐다면, 지금의 데이터 흐름을 완전히 바꿔야 할 수도 있습니다.

> ### Redux의 구조에 대해서 설명해주세요

- 상태가 변경되어야 하는 이벤트가 발생하면, 변경될 상태에 대한 정보가 담긴 Action 객체가 생성됩니다.
- 이 Action 객체는 Dispatch 함수의 인자로 전달합니다.
- Dispatch 함수는 Action 객체를 Reducer 함수로 전달하고
- Reducer 함수는 Action 객체의 값을 확인하고, 그 값에 따라 전역 상태 저장소 Store의 상태를 변경합니다.
- 이 후 상태가 변경되면, React는 화면을 다시 렌더링합니다.

> ### Redux의 장점에 대해서 설명해주세요

- Redux는 스토어라는 이름의 전역 자바스크립트 변수를 통해 상태를 한 곳에서 관리하기 때문에  웹 사이트의 상태를 어디에 둘지 고민하지 않아도 됩니다. 그리고
- 리액트에는 상태(state)라는 개념이 존재합니다. 리액트의 상태는 Redux와 마찬가지로 읽기 전용이며, setState()를 통해서만 상태를 변경할 수 있도록 합니다.
- 서로 유사한 성질로 인해 Redux는 리액트의 상태 관리 도구로 많이 사용되고 있습니다.
- 단점은 전역상태관리를 위한 초기 세팅이 복잡하고 코드량이 많습니다. 그리고 비동기 데이터를 관리하기 위해선 리덕스 thunk와 리덕스 saga라는 미들웨어를 사용해야합니다.

> ### Recoil에 대해서

- recoil은 react에서 useState를 사용하는 방식과 비슷하게 스테이트를 관리할 수 있기 때문에 redux에비해 간단한 코드로 스테이트를 관리할 수 있고 비동기 데이터 또한 내장된 기능인 selector를 활용해 추가적인 미들웨어의 사용 없이 쉽게 비동기 로직을 구현할 수 있습니다.
- selector를 활용해 비동기 통신을 하였을 때 체감되는 강력한 기능은 캐싱 입니다. selector를 활용해 비동기 통신을 해온다면, 내부적으로 알아서 값을 캐싱 해주기 때문에 이미 한번 비동기 통신을 하여 값이 캐싱되어 있다면 매번 같은 비동기 통신을 하지 않고 캐싱 된 값을 추적하여 사용합니다.
