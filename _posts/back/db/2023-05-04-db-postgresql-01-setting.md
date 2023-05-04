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
  postgres=# CREATE DATABASE postgres;
  CREATE DATABASE
  # postgres라는 이름의 데이터베이스를 생성한다.(이름은 자유롭게)

  postgres=# GRANT ALL PRIVILEGES ON DATABASE postgres TO postgres;
  GRANT
  # postgres라는 이름의 계정에 postgres라는 이름의 데이터베이스에 모든 권한을 부여한다.
  ```

## 2. dbeaver
### 2.1 dbeaver 설치(homebrew)
- ```bash
  $ brew install --cask dbeaver-community
  ```

## CLOSING

> 개발환경 세팅은 다했으니 다음에는 flutter를 이용해 앱을 만들어보자!

## RECOMMEND NEXT POSTS

> 없음

### REFERENCE

> 없음
