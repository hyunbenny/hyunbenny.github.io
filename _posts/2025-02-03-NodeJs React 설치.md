---
layout: single
title: NodeJs와 React Framework 설치하기
categories: [NodeJs]
tags: [NodeJs, React, 설치]
toc: true
toc_sticky: true
toc_label: 목차
author_profile: false
sidebar: false
nav: "docs"
search: true
---

# 1. NodeJs /  React Framework 설치

```bash
npm i -g n // global로 n 설치

n lts

n -h
```

### nvm 설치
```bash
brew install nvm

# nvm 디렉토리 생성
mkdir ~/.nvm

# 환경변수 설정
vi ~/.zshrc
export NVM_DIR=~/.nvm
source $(brew --prefix nvm)/nvm.sh

source ~/.zshrc

# bash인 경우
vi ~/.bash_profile
export NVM_DIR="$HOME/.nvm"
[ -s "/usr/local/opt/nvm/nvm.sh" ] && . "/usr/local/opt/nvm/nvm.sh"
[ -s "/usr/local/opt/nvm/etc/bash_completion" ] && . "/usr/local/opt/nvm/etc/bash_completion"

source ~/.bash_profile

```

### node 버전 관리
```bash
nvm ls

nvm install 14.16.1
nvm use 14.16.1

nvm install 17.5.0
nvm uninstall 17.5.0

# default 버전 설정
nvm alias default v14.16.1

node -v
node --version
```

#homebrew
`homebrew`가 설치되어 있지 않은 경우
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```


# 리액트 설치 및 구동
```bash
npm install -g create-react-app # 운영체제에 설치

cd `/Users/hbcho/Desktop/nodeProject`

create-react-app client #react 프로젝트 생성
cd client

npm start # react 서버 구동
```
`localhost:3000` 으로 리액트 서버 구동 확인


```bash
# 글로벌 express-generator 설치
npm i -g express-generator 


#node 프로젝트 생성
cd `/Users/hbcho/Desktop/nodeProject`
express node-project

# 필요 패키지 설치
cd nodeProject
npm install

# 노드 서버 구동
npm start
```
`localhost:3000`으로 노드 서버 확인
![](/assets/images/20250203/NodeJs/1.png)

