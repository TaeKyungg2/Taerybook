---
description: git and github commend, solve error way..
icon: cat
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Git, Github

## [https://github.com/](https://github.com/)

### git 소개

git 이란, 버전 관리 프로그램으로, 오픈소스인 linux 프로젝트를 관리하기 위해 처음 만들어졌다.&#x20;

* 수정 과정을 저장할  수 있다.&#x20;
* 여러 사람이 협업할 때 branch로 안전하게 합치고 정리할 수 있다.
* 문제가 생길  시, 이전 버전으로 돌아갈 수 있다.
* 인터넷 없는 환경에서도 commit 이 가능하다.

git 을 활용해서 파일을 정리하는 사이트 중 대표적인 곳이 github 이다.

### git 기본 개념

먼저, git 의 개념부터 알아보자.\
git 을 사용할 폴더에서, `add`를 하면, 그 폴더에서 관리할 파일들을 정한다.\
`git commit` 을 하면, `add` 한 파일들이 변경된 것들을 저장한다.  이전에  저장되어  있는  것이  있다면,   그것들도  삭제되지  않고  저장되어  있다. `push` 를 하면, github 에 올라간다. github 에서도, 이전 버전들이 저장되어 있다. 그 버전들을 되돌리고, 다시 돌아가고, 할 수 있는 것이다.

### git 사용법

* git 을 설치한다. github 에  가입한다. (생략)
* github desktop 등의 gui 화면을 보면서 할 수 있는 프로그램이 있다. 하지만 터미널로도 쉽게 할 수 있으므로 터미널(cli) 사용하는 방법을 주로 쓴다
* git 으로 관리할 폴더를 만드는 법은 크게 2가지가 있다.
  * 내 컴퓨터에 폴더를 먼저 만든다.
    * 터미널에서 `cd 폴더명` 을 해서, git 으로 관리하고자 하는 폴더에 들어간다.
    * `git init` 를 하면 그 폴더가 git 이 관리되는 폴더로 바뀐다.(숨김 폴더 .git 이 생긴다.)
    * (여기까지 해도 commit 까지 가능하고, 그러므로 버전 관리가 가능하다.)
    * github 사이트에서 repository 를 만들고, `<>code` ,`HTTP` 버튼을 차례대로 누른 후 링크를 복사한다. 내 컴퓨터에서 이 repository 에 연결하기 위한 주소이다.
    * github
