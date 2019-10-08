---
title: 블로그 관리를 위한 Git 기본 / github
date: "2019-10-04T22:40:32.169Z"
template: "post"
draft: false
slug: "/posts/basic-of-git/"
category: "Frontend basic"
tags:
  - "Web Development"
  - "Frontend"
  - "Git"
description: "개발자라면 알아야 할 git과 github에 대해 알아보자"
socialImage: "/media/42-line-bible.jpg"
---

## git은 쉽게 파일을 관리하기 위한 명령어다.

### 1. blog 설치

blog를 처음부터 하나하나 만드는 데는 시간이 한참 걸리기 때문에 블로그를 만들어 주는 site generator를 쓴다.  
여기서는 Gatsby를 쓸 것이다.

Gatsby로 블로그를 쓰기로 했기 때문에 Gatsby 명령어를 설치한다.
<pre><code>
  npm install -g gatsby-cli
</code></pre>

여기서 npm은 *node package manager* 약자다.

npm에 대한 개념이 모호해서 검색해봤다.

package는 어플리케이션, 소프트웨어와 비슷한 개념이다.  
스마트폰에서 앱스토어나 구글플레이를 통해 어플을 검색하고 설치하거나 업데이트하고 삭제하는 것처럼 개발자도 소프트웨어를 설치, 삭제 하는 곳이 필요한데 npm이 바로 그 파일들을 모아놓은 저장소라고 생각하면 된다. 

Gatsby 명령어를 설치했으므로 Gatsby에서 원하는 테마의 source code를 가져와야 한다.

<pre><code>
gatsby new blog  https://github.com/alxshelepenok/gatsby-starter-lumen
</code></pre>

잘 설치됐는지 확인하려면 blog로 이동해서 파일을 화인하면 된다.

여기서 디렉토리 이동 문법은  
<pre><code>cd 디렉토리이름/</code></pre>

그리고 안의 파일 확인 하려면 ls  
현재 경로를 알고 싶을 때는 pwd

### 2. 서버 생성

이제는 블로그를 실시간으로 점검하기 위해서는 서버가 필요하다.
<pre><code>npm run develop</code></pre>

DONE Compiled successfully 라고 뜨면 성공!  
localhost:8000 으로 접속하면 위에서 골랐던 blog 테마가 나온다! **성공!!**  
내 컴퓨터에서 이 터미널 창을 통해 서버 하나를 생성한 것이므로  
이 창을 끄면 *페이지가 열리지 않는다.*

서버를 멈추고 싶으면 띄어놓은 터미널 창에서 Ctrl + C  

### 3. 블로그 세팅 수정

블로그 세팅을 몇 가지 수정해야 한다.  
config.js 파일을 찾아서 title, author 등 정보를 수정하면 된다.

이유는 잘 모르겠지만 메인페이지에서는 저장하면서 실시간으로 바뀌고 있지는 않다.  
하지만 블로그 글은 실시간으로 수정 가능하다.  
현재 그렇게 바뀌는 걸 실시간으로 확인하면서 수정하고 있다.

그리고 package.json 파일을 찾아서 "script" 아래 부분의 "deploy"를 아래와 같이 바꿔준다.
<pre><code>"deploy": "yarn run clean && gatsby build && gh-pages -d public -b master",</code></pre>

이렇게 세팅을 수정하고 <code>npm run deploy</code>를 하게 되면 github에 내 소스코드를 보내게 된다.

### 4. github repo 생성

이렇게 만든 blog를 세상 앞에 선보일 시간이다.  
개발자 언어로는 **deploy** 또는 **배포**라고 한다.  

나만의 블로그를 위해서는 도메인을 따로 구입해야 하지만  
정말 감사하게도 github에서 도메인을 제공해준다.  
그걸 사용하는 방법을 알아보자.

먼저 github 사이트에 들어가서 repository, 즉, 저장소를 만들어야 한다.  
이 때 주소를 username.github.io 라고 입력해야 한다.  
username에는 가입했을 때의 username을 적으면 된다.

### 5. github 연결하기

저장소도 만들었으니 열심히 만든 블로그를 저장소에 보내는 일만 남았다.  
소스코드를 github로 보내려면 내 컴퓨터에 있는 blog파일과 github를 연결해야 한다.

<pre><code>git init</code></pre>  
<pre><code>git remote add origin https://github.com/username/username.github.io.git</code></pre>
위의 username부분을 본인의 username으로 바꿔주고 실행한다.  
여기서 origin은 github를 의미한다.  
아무런 반응이 일어나지 않으므로 잘 연결 됐는지 확인해야 한다.
<pre><code>git remote -v</code></pre>

이렇게 한 번 연결해두면 다음 번에 수정해서 배포할 때는 이 연결 과정을 거치지 않아도 된다.

### 6. 배포하기

github와 연결 했으니 이제 보낼 일만 남았다.  
코드를 보내는 것을 개발자 언어로 **push**라고 한다.

push 해보자.

<pre><code>git add .</pre></code>
<pre><code>git commit -m "적을 메세지"</pre></code>
<pre><code>git push origin master</pre></code>

여기까지 하고 github로 가서 소스코드가 잘 올라왔는지 확인한다.  
잘 됐으면 배포 명령어를 실행할 때다.
<pre><code>npm run deploy</pre></code>

github를 가서 확인해보면 md 파일이 모두 html, js로 자동변환돼서 올라가 있다.  

현재는 master branch에 push를 하고 있지만 개발코드를 따로 보관하기 위해서  
branch 하나를 더 만들기로 하자.
<pre><code>git branch develop</code></pre>
<pre><code>git checkout develop</code></pre>
첫 번째는 develop이라는 이름을 가진 branch를 만드는 명령어이고  
두 번째는 develop이라는 이름을 가진 branch를 사용하겠다고 지정하는 명령어이다.  
그리고 새로 지정한 develop branch에서 push를 해보자.

<pre><code>git add .</pre></code>
<pre><code>git commit -m "적을 메세지"</pre></code>
<pre><code>git push -u origin develop</pre></code>

앞으로 계속 develop branch에 push하기 위해  
github에 들어가서 해당 블로그의 repo의 setting에서  
branch default 값을 master에서 develop으로 바꿔준다!