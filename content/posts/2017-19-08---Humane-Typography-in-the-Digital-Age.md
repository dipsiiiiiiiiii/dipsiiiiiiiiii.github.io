---
title: HTML/CSS를 이용한 Layout
date: "2017-08-19T22:40:32.169Z"
template: "post"
draft: false
slug: "/posts/humane-typography-in-the-digital-age/"
category: "Typography"
tags:
  - "Design"
  - "Typography"
  - "Web Development"
description: "An Essay on Typography by Eric Gill takes the reader back to the year 1930. The year when a conflict between two worlds came to its term. The machines of the industrial world finally took over the handicrafts."
socialImage: "/media/42-line-bible.jpg"
---


# 1. Position

브라우저 내에서의 엘리먼트들의 위치를 선정할 수 있다.(Layout)  
Static, Relative, Absolute, Fixed 4가지가 있다.  
- Static : default값(static이라고 써주지 않아도 된다)  
	엘리먼트가 차례대로 왼쪽에서 오른쪽, 위에서 아래로 쌓인다.

- Relative : Static 상태 기준으로 상하좌우로 위치 조절 가능(property : top, right, bottom, left)  
+값 : 내부 영역방향으로 이동  
-값 : 외부 영역방향으로 이동  
별도의 property값을 주지 않으면 static과 같다.  
※ body태그 이외에 어디에 상속되지 않은 상태로 relative값을 받으면 화면 전체를 기준으로 움직이더라.