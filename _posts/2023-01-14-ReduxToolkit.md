---
layout: single
title: "Redux?"
excerpt: "Redux의 개념과 Redux-toolkit"

categories:
  - React

tags:
  - [React, Redux, Redux-toolkit]

date: 2023-01-14
published: true
---

## Redux란?

> 리덕스는 자바스크립트 앱을 위한 예측 가능한 상태 컨테이너 입니다.

리덕스의 공식 홈페이지에서는 리덕스를 위와 같이 설명하고 있습니다. 하지만 썩 이해하기 쉽지는 않죠,

쉽게 말하면 리덕스는 중앙 상태 관리 라이브러리 입니다. 리액트로 어플리케이션을 개발하다보면 state를 변경해야하는 상황이 빈번히 발생합니다. 이때 우리가 원하는 state가 자식 컴포넌트의 자식 컴포넌트에 있다면 props를 내리고 또 내려야 하는 상황이 발생하죠, 이렇게 된면 코드를 리팩터링 하거나 버그를 잡아야 할 때 더 많은 시간과 노력이 필요하게 됩니다.

이런 상황과 문제를 해결하기 위해 중앙 상태 관리 라이브러리가 존재하고, 리덕스는 이런 중앙 상태 관리 라이브러리의 한 종류 입니다. 리덕스 홈페이지의 설명에 따라 리덕스는 리액트 환경에서 뿐만 아니라 다른 환경에서도 사용이 가능한 라이브러리 이지만 리액트 환경에서의 쓰임이 많은 편 입니다.

또한, 리액트 환경에서는 ContextAPI, Recoil 등 과 같은 다양한 방법으로도 중앙 상태 관리 환경을 구성할 수 있습니다.

## 왜 Redux 일까?

> ContextAPI와의 비교

리덕스와 ContextAPI는 궁극적으로 같은 기능을 수행하기 때문에 동작 과정에서도 닮은 부분이 많습니다.
하지만 리덕스는 Context API와 달리 전역 상태 관리 이 외에도 다양한 기능을 제공하고 이로 인해 더 정교한 작업이 가능합니다. 이런 정교한 작업과정은 TDD에 더 유리한 결과를 환경을 제공합니다.

- 사용자의 액션을 직렬화해서 상태와 함께 자동으로 버그 리포트에 첨부 할 수 있습니다.
- 액션 객체를 네트워크를 통해 보내면 코드를 크게 바꾸지 않고도 협업 환경을 구현할 수 있습니다.
- 실행 취소 내역의 관리를 코드를 크게 바꾸지 않고도 구현 할 수 있습니다.
- 개발할 때 상태 내역 사이를 오가고 액션 내역에서 현재 상태를 다시 계산하는 일을 TDD스타일로 할 수 있습니다.
- 개발자 도구에게 완전한 조사와 제어를 가능하게 해서 개발자들이 자신의 앱을 위한 도구를 직접 만들 수 있게 해줍니다.

위의 글은 Dan Abranov에 글에서 발췌한 부분입니다.

다시 한번 정리해 보면 리덕스는 redux-saga, redux-thunk 등 다양한 추가 라이브러리를 통해 조금 더 세밀한 상태관리가 가능하고 정교한 프로그래밍을 가능하게 합니다.

## Redux-toolkit은 뭘까?

Redux-toolkit(이하 RTX)은 Redux에서 공식 제공하는 라이브러리입니다.
리덕스에서 이처럼 추가적인 라이브러리를 제공하는 이유는 무엇일까요?

1. 리덕스는 저장소 구성이 복잡합니다.
2. 리덕스는 immer, reselector, thunk 등 필요에 따라 다른 패키지들을 필요로 하기때문에 의존성에 취약점을 갖습니다.
3. 작업을 진행 할 때 작성해야 할 코드의 양이 비교적 많습니다.

이러한 점들을 보완하고자 rtx가 존재합니다.

## Redux-toolkit 사용법(typescript)

1. Root State & Dispath Types
   ​

```typescript
import { configureStore } from "@reduxjs/toolkit";
// ...
export const store = configureStore({
  reducer: {
    posts: postsReducer,
    //슬라이스 예시
  },
});
// RootState에 대한 타입 지정
export type RootState = ReturnType<typeof store.getState>;
// dispatch에 대한 타입 지정
export type AppDispatch = typeof store.dispatch;
```

2. Hooks에 대한 타입 지정
   ​

```typescript
import { useDispatch, useSelector } from "react-redux";
import type { TypedUseSelectorHook } from "react-redux";
import type { RootState, AppDispatch } from "./store";
// app내에서 useAppDispatch나 Selector를 사용할때 타입을 지정해줘야 하므로 전역적으로 타입을 지정해준다.
export const useAppDispatch: () => AppDispatch = useDispatch;
export const useAppSelector: TypedUseSelectorHook<RootState> = useSelector;
```

3. Slice 생성 Action Types 지정

```typescript
import { createSlice } from "@reduxjs/toolkit";
import type { PayloadAction } from "@reduxjs/toolkit";
import type { RootState } from "../../app/store";
// 슬라이스 타입 지정
interface CounterState {
  value: number;
}
// Define the initial state using that type
const initialState: CounterState = {
  value: 0,
};
export const counterSlice = createSlice({
  name: "counter",
  // `createSlice` will infer the state type from the `initialState` argument
  initialState,
  reducers: {
    //action예시
    incrementByAmount: (state, action: PayloadAction<number>) => {
      state.value += action.payload;
    },
  },
});
export const { increment, decrement, incrementByAmount } = counterSlice.actions;
// Other code such as selectors can use the imported `RootState` type
export default counterSlice.reducer;
```

​

### RTX 동작과정

![RTX동작과정](https://facebook.github.io/flux/img/overview/flux-simple-f8-diagram-explained-1300w.png)
