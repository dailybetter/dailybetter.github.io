---
layout: single
title:  "React란 무엇일까?"
excerpt: "React의 개념과 NodeJs"

categories:
- React

tags:
- [React, vite]

date: 2022-11-9
published: true
---
## React 란 무엇인가?

리액트를 학습하기 앞서 리액트라는 라이브러리가 왜 만들어졌는지 알아보자!
JavaScript를 사용하여 HTML로 구성한 UI를 제어해본경험이 있다면 DOM을 변형시키기 위해서 어떤 작업을 해야하는지 알 것이다. DOM Selector API를 사용해서 특정 DOM을 선택한 뒤 이벤트가 발생될 때 특정 작업을 수행하도록 하나하나 코드를 입력해줘야 하는 기존 JS 특성 상 사용자와의 인터랙션이 자주 발생하는 환경이라면 코드가 길어지고 복잡해지기 마련이다.

이러한 문제점을 해결하고자 AngularJS, Backbone, Ember 등의 프레임워크가 만들어졌고 이들은 특정 JS 속성이 바뀌면 DOM의 속성이 바뀌도록 연결해주어서 업데이트 하는 작업을 간소화 해주는 방식을 채택 했다.

하지만 리액트는 위의 것들과 조금 다른 발상에서 만들어졌다. 리액트는 기존 DOM을 수정, 업데이트 하는 방식이 아닌 메모리에 가상으로 존재하는 Virtual DOM을 만들어서 보여줌으로서 기존 방식보다 훨씬 빠른 서비스를 제공한다.


## React 초기 설정 방법

1. NodeJs 설치
    - [nodejs 홈페이지](https://nodejs.org/ko/download/)에서 버전 선택 후 다운로드
2. 터미널을 통해 'npx create-react-app app이름' 입력

3. 끝!

리액트를 setup 할 수 있는 방법은 여러가지라서 본인이 필요로 하는 방법에 맞춰 setup하는 것이 좋다.

### NodeJs를 설치하는 이유

- NodeJs란 JS 런타임 환경 이다.
- 웹서버와 같이 확장성 있는 네트워크 프로그램을 제작하기 위해 만들어졌다.
- NodeJs 는 npm, npx 와 같은 다양한 모듈을 제공한다. 이런 모듈을 통해 react 라이브러리와 react라이브러리에서 사용되는 다양한 기능들을 쉽고 빠르게 설치 할 수 있다.
