---
layout: single
title:  "Github pages 만들기01-이미지 삽입"
excerpt: "이미지를 삽입하는 여러가지 방법"

categories:
- Github Blog
tags:
- [Blog, jekyll, Github, Git]

date: 2022-03-29
published: true
---
오늘은 github pages에 이미지를 삽입하는 방법을 배워보고 실제로 적용해보도록 하자!

## 서론

sidebar, topbar, favicon 등등 해야될 작업들이 수두룩하지만 앞으로 진행항 작업들의 진행상황과 
그에따라 발생하는 문제들과 해결방법을 포스팅하기 위해 우선은 post에 이미지를 삽입하는 방법을 배워보려한다.
또한 블로그를 개설하고 수정보안하는데 많은 뛰어난 분들의 blog와 post를 참고해서 제작하고자 한다.
자료출처는 post하단에 남겨놓을 예정이니 참고하길 바란다.

## 본론

### 마크다운 문법

나의 Github 블로그는 지킬 이라는 사이트 생성기를 통해 만들었고 이는 마크다운 문법을 통해 포스팅을 할수 있다. 
그러므로 정석대로 마크다운 문법에 맞게 이미지를 삽입하면 된다.
나는 [Github Docs](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)를 참고하였다.
비록 영어로 되어있긴하지만 가독성이 뛰어나고 번역기만 있다면 누구나 쉽게 이해할수 있을만한 수준으로 설명되어 있다

문서에 따른 업로드 방법은 아래와 같다.

```
![Some Img](/images/images)
```


이미지의 이름과 그 위치를 적으면 되는것 같으니 우선 해보도록하겠다.
![testimg](/assets/images/iconic.png)

