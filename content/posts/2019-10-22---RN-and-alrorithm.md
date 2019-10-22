---
title: "[TIL] 2019.10.22. 알고리즘 접근법, React-Native 문법"
date: "2019-10-22T15:40:32.169Z"
template: "post"
draft: false
slug: "/posts/20191022-til/"
category: "TIL"
tags:
  - "Web Development"
  - "Frontend"
  - "TIL"
  - "Algorithms"
  - "React-Native"
description: "Today I Learned"
socialImage: ""
---

# 알고리즘 세션
## 풀이 접근 과정

1. 문제를 완벽히 이해 > 확인 과정까지!! ex)제가 이해하기로는 …  
문제 이해는 input, output으로 정리.
2. 코드 하다가 막히는 게 아니라 처음부터 다 완벽하게 짜고 코드는 맨 마지막에 작성하기 시작해야 한다.
3. 내 생각 과정을 말 하면서 해야 한다.
4. 문제 맞추는 거는 당연히 중요하지만 그 과정을 말을 함으로써 내가 어떻게 접근하는 지를 전달하는 것도 중요하다.
5. 면접할 때 면접관이 힌트를 주게끔 해야 한다. 면접관과의 케미 중요!!


## 해결책 구하는 방법
AI의 시발점 : 사람의 생각은 무수한 if의 연속이다.  
아무리 복잡한 것도 binary decision 으로 나눠질 수 있다!  
알고리즘 문제도 똑같다.

시작점을 정하고 binary decision!  
알고리즘 구조 그림을 그려서 해결 방향을 찾고 코드를 그리겠다고 말하고 코드 그림!  
코드 다 짜고나서 test꼭 해봐야 한다. Test input을 정해서 넣어보면 된다.  
Test output expected를 정해서 expected와 실제 output을 비교한다.  
만약 expected와 다르다면 debugging 해야 된다. 검증 필수!!  
막혀있을 때도 왜 막혀 있는지 어떻게 접근하려고 했는지 항상 말해줘야 한다.


1. 인성(이력서 베이스, 말투, 행동, 옷)
2. 지식 실력
3. 코딩 실력

# React-Native 문법

## style
이미지를 원으로 만들기 위해서는 borderRadius는 react에서는 50%로 줄 수 없어서 height의 절반 값으로 줘야 한다.

props에서 안드로이드는 uri만 되고 ios는 uri, url둘 다 된다.  
uri를 쓰자.

자식 컴포넌트에서 flex값으로 부모 크기를 기준으로 비율에 따라 나눌 수 있다.

Image를 넣어주려면 Image 컴포넌트에 source prop으로 넣어야 한다.  

z-index가 없지만 RN은 무조건 뒤에 있는 컴포넌트을 맨 위로 올려둡니다.

가장 위로 올리고 싶은 컴포넌트를 제일 마지막에 두면 된다.

기본적으로 display: flex가 설정되어 있다.

에러 코드 500이면 경로 문제일 가능성 높음.

## Flat List

FlatList 컴포넌트는 props로 항상 data와 renderItem을 가지고 있다.  
JavaScript ES6 문법의 map과 역할이 비슷하다.  
data는 다른 파일에 저장해주고 import를 통해 가져오는 방법으로 관리해야 한다.  
renderItem은 argument로 항상 {item}을 받아야 한다.  
id는 string타입으로만 항상 받아야 한다.

```JS
import React, {Component} from 'react'
import { FlatList } from 'react-native'
import DATA from './DATA'

/*
const DATA = [{
    id: 'asdfsvwe',
    key1: 'value1',
}, {
    id: 'agwrwadsf',
    key2: 'value2'
}]
*/

class FlatList extends Component {
constructor(){
    super()
    this.state = {
        data = {DATA}
    }
}

<FlatList 
    data={this.state.data}
    renderItem={({item}) => 
    <Component props1={items.key1} props2={items.key2} /> }
    keyExtractor={item => item.id}
/>
}

```

## JavaScript TIL

button태그에는 onSubmit이 적용이 안된다.