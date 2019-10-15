---
title: "[instagram 클론 시리즈] 기초가 중요하다!"
date: "2019-10-08T11:08:32.169Z"
template: "post"
draft: false
slug: "/posts/westagram-1/"
category: "Clone Coding"
tags:
  - "Web Development"
  - "Frontend"
  - "Git"
description: "똑같이 따라 만들어 보자"
socialImage: ""
---

## *삽질 지식*

### 인스타그램 프로필 사진 동그랗게
border-radius: 50%;

### 버튼태그가 form 태그 안에 있으면 submit 기능이 default;
submit 기능 : 자동으로 리로드 된다.

### innerHTML 이랑 value 차이??
userId를 가져오는 건 innerHTML  
textarea태그에 쓴 댓글을 가져오는 건 value << 쓴 댓글이 value로 들어가기 때문

### Append 해줄 때 class이름으로 가져올 때
index값 꼭 넣자.

### value값 초기화 할 때
<pre><code>element.value = null;</code></pre>

### dom으로 style 접근할 때
값을 가져오는게 아니라 직접 넣어줘야 한다.  
값을 가져오지는 않는다.

### 퍼센트로 길이를 주는 건 조심해야 한다.
대신 전체 틀이 되는 길이는 고정값으로 주자.

### 번외) git 명령어, blog

기존에 연결돼있는 저장소 삭제 : <code>Git remote remove origin</code>

Blog 상단 아이콘은 정사각형이어야 한다!!