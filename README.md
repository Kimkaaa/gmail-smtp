# Gmail SMTP Mail (Spring Boot)

<br>

Gmail SMTP를 활용하여 Spring Boot 환경에서

**텍스트 · HTML 템플릿 · 첨부파일 메일** 전송 기능을 구현한 프로젝트입니다.

테스트 화면을 통해 메일 전송 기능을 직접 확인할 수 있습니다.

<br>

> 관련 내용은 [블로그 글](https://velog.io/@kimkaaa/Spring-Boot-Gmail-SMTP%EB%A1%9C-%ED%85%8D%EC%8A%A4%ED%8A%B8HTML%EC%B2%A8%EB%B6%80%ED%8C%8C%EC%9D%BC-%EB%A9%94%EC%9D%BC-%EB%B3%B4%EB%82%B4%EA%B8%B0)에서 확인할 수 있습니다.

<br>

## 주요 기능

- 텍스트 메일 전송
- HTML 템플릿 메일 전송
- 첨부파일 메일 전송

<br>

## 기술 스택

- Java 17
- Spring Boot 3.4.12
- Thymeleaf

<br>

## 실행 화면
![000_폼_UI.png](src%2Fmain%2Fresources%2Fstatic%2Fimages%2F000_%ED%8F%BC_UI.png)

<br>

## 실행 결과

![002_결과.png](src%2Fmain%2Fresources%2Fstatic%2Fimages%2F002_%EA%B2%B0%EA%B3%BC.png)

<br>

## Gmail SMTP 설정 방법

1. Google 계정 → **보안** → 2단계 인증 활성화
2. 검색창에 **앱 비밀번호** 입력
3. 앱 비밀번호 생성 → 16자리 비밀번호 복사
4. 이 값을 `mail.password`로 사용

⚠ **주의:** Gmail 계정 비밀번호가 아니라 반드시 **앱 비밀번호**를 사용해야 합니다.

<br>

## application.yml 설정 예시

```yaml
spring:
  mail:
    host: smtp.gmail.com
    port: 587
    username: ${mail.username}
    password: ${mail.password}
    properties:
      mail:
        smtp:
          auth: true
          timeout: 5000
          starttls:
            enable: true
```

<br>

## 테스트 페이지 경로

프로젝트 실행 후 아래 URL에서 메일 전송 테스트를 진행할 수 있습니다.

| 메일 타입 | URL |
| --- | --- |
| 텍스트 메일 | http://localhost:8080/mail/form/text |
| HTML 메일 | http://localhost:8080/mail/form/html |
| 첨부파일 메일 | http://localhost:8080/mail/form/attachment |
