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

# 서론

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


이미지의 이름과 그 위치를 적으면 되는것 같으니 우선 해보도록하겠다.<br>
![testimg](/assets/images/iconic.png)

정상적으로 이미지가 업로드 된것을 확인할 수 있다.

### 깃허브 ISSUE 활용하기

github page에 이미지를 업로드하는 다른 방법으로 [issues](https://github.com/dailybetter/dailybetter.github.io/issues) 를 활용하는 방법이 있다
- issues는 본래 project를 진행하며 발생하는 모든 이슈들을 뜻합니다. ex. 버그 발생, 개발, 풀 리퀘스트 등등..
- 그리고 이런것들을 효율적으로 관리하고자 존재하는것이 issues 탭이죠
- 위 링크를 통해 직접 들어가보면 어떤 기능인지 쉽게 알 수 있습니다.
**그럼 어떻게 issues를 이용해서 img를 업로드 할까요**
방법은 매우 간단합니다.
1. Issues탬에 가서 New issues를 누릅니다![issues](https://user-images.githubusercontent.com/101924720/160527482-15b94972-b3fb-43eb-8d67-3af620a40970.png)
2. 이미지 파일을 textbox에 드래그 앤 드롭 하거나 붙여넣습니다.
3. 마크다운 문법으로 자동 생성된 이미지 주소를 복사하여 md파일에 붙여넣습니다.<br>
**끝**

- 이는 이미지가 쌓여갈수록 repo가 무거워지는것을 방지할 수 있는 장점이 있지만 정식적인 방법은 아니라고 생각된다
<br>
- 자료 출처 및 참고 사이트
- [Github Doc](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [Hyeon JiWon님 블로그](https://hyeonjiwon.github.io/blog/markdown_img/)
- 그 외 구글링