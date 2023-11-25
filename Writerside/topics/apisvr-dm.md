# apisvr-dm

# 송아리 당뇨 DM API Server Back-End Project
> DM : Diabetes Melitus(당뇨병)의 약자


## 목차

- ### [프로젝트 환경](#프로젝트-환경)
- ### [프로젝트 구조](#프로젝트-구조)
- ### [사용한 라이브러리들](#사용한-라이브러리들)
- ### [기동 방법](#기동-방법)


## 프로젝트 환경

- ### Java : 17
- ### Spring Boot : 3.1.4
- ### Maven


## 프로젝트 구조
```text

.
├── main
│   ├── java
│   │   └── com
│   │       └── songareeit
│   │           └── apsvrdm
│   │               ├── ApisvrDmApplication.java
│   │               ├── common
│   │               ├── config
│   │               ├── endpoint
│   │               ├── model
│   │               ├── payload
│   │               ├── repository
│   │               ├── security
│   │               └── service
│   └── resources
│       └── ...
└── ...
```


## 사용한 라이브러리들

- ### spring-boot-starter-data-jpa
- ### spring-boot-starter-web
- ### spring-boot-starter-undertow
- ### spring-boot-starter-validation
- ### spring-boot-starter-security
- ### spring-restdocs-mockmvc
- ### lombok
- ### mysql-connector-java
- ### [jasypt-spring-boot-starter](https://github.com/ulisesbocchio/jasypt-spring-boot) : 설정 파일 암호화에 사용
- ### aws-java-sdk-s3 : 파일 저장시 AWS S3에 저장하기 위해 사용
- ### [jjwt-api, jjwt-impl, jjwt-jackson](https://github.com/jwtk/jjwt) : JWT 생성을 위함
- ### commons-fileupload : 파일 다운로드 시 바이트 코드 변환에 사용
- ### commons-codec : AES128 암호화시 바이트코드 인코딩에 사용


## 기동 방법

> 현재 application.yml 에서 몇몇 설정 값들이 `ENC({암호화된 문자열})` 꼴로 암호화 되어 있어,
> 실행 시점에 이를 복호화하기 위한 키(password)가 필요

### 1. IDE (IntelliJ 기준)

- Run/Debug Configuration → Add VM options → `-Djasypt.encryptor.password={비밀번호}` 입력,
- 필요 시 Active profiles (`dev`, `stage`)입력

- ![ide-starting-sercer.png](ide-starting-sercer.png)

### 2. CLI

- 프로젝트 빌드 방법
    - 프로젝트 루트에서 `mvn package -Djasypt.encryptor.password={비밀번호}` 입력

- 프로젝트 실행 방법
    - 프로젝트 루트에서 `./start.sh` 를 입력하여 실행 스크립트 실행

- 프로젝트 중지 방법
    - 프로젝트 루트에서 `./stop.sh` 를 입력하여 중지 스크립트 실행
