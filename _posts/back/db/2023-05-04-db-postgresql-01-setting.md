---
layout: single
title: "[postgresql] - 01. Mac M1 환경에서 설치 및 세팅하기(dbeaver)"
date: "2023-05-04 00:00:00 +0900"
last_modified_at: "2023-05-04 00:00:00 +0900"
categories:
  - back-db
tags:
  - DB
  - postgresql
# toc_label: "목차"
# toc: true
# toc_sticky: true
---

<br/>

## RECOMMEND BEFORE POSTS

> 없음

## 0. 들어가면서

> Mac M1 환경에서 postgresql을 설치하고 세팅하자. <br> > [stackoverflow survey 2022](https://survey.stackoverflow.co/2022/#section-most-popular-technologies-databases) 에서 All Respondents 기준 2위, Professional Developers 기준 1위를 차지한 postgresql을 공부해보자.

## 1. postgresql

### 1.1 homebrew로 설치하기

- ```bash
  $ brew install postgresql
  ```

### 1.2 postgresql 실행하기

- ```bash
  $ brew services start postgresql
  ```

### 1.3 postgresql 접속하기

- ```bash
  $ psql postgres
  ```

### 1.4 로컬 개발을 위한 계정 생성 및 권한 추가

- ```bash
  postgres=# CREATE ROLE postgres WITH LOGIN PASSWORD 'postgres';
  CREATE ROLE
  # postgres라는 이름의 계정을 생성하고 비밀번호는 postgres로 설정한다.

  postgres=# ALTER ROLE postgres CREATEDB;
  ALTER ROLE
  # postgres라는 이름의 계정에 데이터베이스 생성 권한을 부여한다.

  postgres=# ALTER ROLE postgres CREATEROLE;
  ALTER ROLE
  # postgres라는 이름의 계정에 데이터베이스 생성 권한을 부여한다.
  ```

### 1.5 로컬 개발을 위한 데이터베이스 생성 및 디비접근 권한 부여

- ```bash
  postgres=# CREATE DATABASE test;
  CREATE DATABASE
  # test라는 이름의 데이터베이스를 생성한다.(이름은 자유롭게)

  postgres=# GRANT ALL PRIVILEGES ON DATABASE test TO postgres;
  GRANT
  # postgres라는 이름의 계정에 test라는 이름의 데이터베이스에 모든 권한을 부여한다.
  ```

### 1.6 유저 확인 및 db 접속

- ```bash
  postgres=# \connect test
  You are now connected to database "test" as user "기본유저".
  # test 데이터베이스에 접속한다.

  test=> \q
  # test 데이터베이스에서 나온다.

  $ psql -U postgres -d test
  # test 데이터베이스에 postgres라는 이름의 계정으로 접속한다.

  test=> select current_user;
  current_user
  -------------
  postgres
  (1 row)
  # 이렇게 생성한 계정으로 생성한 데이터베이스에 접속할 수 있다.

  ```

## 2. dbeaver

### 2.1 dbeaver 설치(homebrew)

- ```bash
  $ brew install --cask dbeaver-community
  ```

### 2.2 dbeaver 실행 및 postgresql 연결

- ```bash
  $ open /Applications/DBeaver.app
  ```
- 그냥 더블클릭으로 실행하자.
- 좌측 상단에 콘센트 모양을 클릭 후 postgresql을 선택하면 된다.
- driver를 다운로드 하라는 팝업이 뜨면 다운로드 하자.
- Authentication에 postgresql 계정 정보(username, pw: postgres)를 입력하고 test connection을 눌러 연결을 확인하자.
- 연결을 확인했다면 완료를 눌러주자.
- 좌측에 디비가 연결된 것을 볼 수 있다!
- 만약 보이지 않는다면 dbeaver를 클릭하고 화면 제일 상단에 윈도우를 눌러 Database Navigator를 클릭하자!

## CLOSING

> 끝! 이제는 실제 스프링 프로젝트랑 연결해보아야겠다.

## RECOMMEND NEXT POSTS

> 없음

### REFERENCE

> 없음
