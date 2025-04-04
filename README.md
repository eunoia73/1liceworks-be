# 🚀 1llis Works
**Illis Works는 팀 단위의 일정 관리와 협업을 효과적으로 수행할 수 있도록 돕는 캘린더 기반 협업 툴입니다.  
팀 캘린더, AI 기반 일정 추천, 실시간 알림 등의 기능을 제공하여 업무 효율성을 높이고 일정 조율을 자동화합니다.**

---

## 📌 기술 스택

### 🔹 백엔드
| 기술 | 버전 |
|---|---|
| ![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white) | OpenJDK 17 |
| ![SpringBoot](https://img.shields.io/badge/SpringBoot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white) | 3.3.1 |
| ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white) | 8.3.0 |
| ![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white) | 3.3.1 |
| ![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black) | 9.1.1 |
| ![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white) | 3.1.0 |
| ![Gemini API](https://img.shields.io/badge/Gemini_2.0_Flash_Lite-4285F4?style=for-the-badge&logo=google&logoColor=white) | Latest |
| ![JUnit5](https://img.shields.io/badge/JUnit5-25A162?style=for-the-badge&logo=junit5&logoColor=white) | 5 |
| ![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white) | Latest |
| ![K6](https://img.shields.io/badge/K6-7D64FF?style=for-the-badge&logo=k6&logoColor=white) | Latest |

### 🔹 배포
| 기술 | 버전 |
|---|---|
| ![GitLab Runner](https://img.shields.io/badge/GitLab%20Runner-FC6D26?style=for-the-badge&logo=gitlab&logoColor=white) | Latest |

---

## 🏗️ 시스템 아키텍처
![아키텍쳐.jpg](images%2F%EC%95%84%ED%82%A4%ED%85%8D%EC%B3%90.jpg)

---

## 🗂 ERD
![ourErd.png](images%2FourErd.png)

---

## API 문서

👉 [Swagger 링크](http://34.22.92.60:8080/swagger-ui/index.html#/)



## 🎨 와이어프레임
👉 [Figma 링크](https://www.figma.com/design/0ODht4QuTq69ygXL72r3wa/%EC%97%98%EB%A6%AC%EC%8A%A4-2%EC%B0%A8-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8?node-id=0-1&p=f&t=kSja9bXIr6XZrzmW-0)

---

## 📜 코드 컨벤션

### 🔹 백엔드
![백컨벤션.png](images%2F%EB%B0%B1%EC%BB%A8%EB%B2%A4%EC%85%98.png)

---

## 🎯 프로젝트 개요

### ✅ 기능
- **인증/인가 기능**:로그인, 회원가입, 로그아웃, 프로필 조회/수정, 비밀번호 변경
- **팀 관리 기능**: 팀 생성, 수정, 삭제, 팀장 위임 및 멤버 관리 기능
- **캘린더 기능**: 팀 캘린더 공유, 일정 생성/수정/삭제 및 개인 일정 관리
- **알림 기능**: SSE 기반 실시간 알림, 일정 변경 및 팀 활동 알림 제공
- **AI 기능**: Gemini API를 활용한 자동 일정 생성 및 최적 일정 추천

---

### 📌 추가 기능
- **캘린더 권한 관리 (팀 캘린더 / 개인 캘린더)**
- **일정 검색 및 필터링**
- **React Query를 활용한 상태 관리 최적화**
- **CI/CD 자동 배포 (GitLab Runner 활용)**

---

## 🎬 프로젝트 데모
![캘린더조회.gif](images%2F%EC%BA%98%EB%A6%B0%EB%8D%94%EC%A1%B0%ED%9A%8C.gif)
---

## 🌍 환경 변수 설정 (application.yaml)

```bash
server:
  port: 8080

spring:
  servlet:
    multipart:
      enabled: true
      max-file-size: 10MB
      max-request-size: 10MB
  application:
    name: iliceworks-be

  cache:
	  type: redis
  data:
    redis:
      host: localhost
      port: 6379

  jpa:
    hibernate:
      ddl-auto: create-drop
    show-sql: true
    properties:
      hibernate:
        format_sql: true
        dialect: org.hibernate.dialect.MySQLDialect
    defer-datasource-initialization: true

  datasource:
    username: "YOUR_USERNAME"
    password: "YOUR_PASSWORD"
    url: jdbc:mysql://localhost:9906/iliceworks?serverTimezone=UTC&characterEncoding=UTF-8
    driver-class-name: com.mysql.cj.jdbc.Driver

  mail:
    host: "YOUR_HOST"
    port: "YOUR_PORT"
    username: "YOUR_USERNAME"
    password: "YOUR_PASSWORD"
    properties:
      smtp:
        auth: true
        timeout: 5000
        starttls:
          enable: true
  cloud:
    compatibility-verifier:
      enabled: false

springdoc:
  api-docs:
    path: /api-docs  # API 문서 기본 경로
  swagger-ui:
    path: /swagger-ui.html  # Swagger UI 경로

token:
  secret: "YOUR_SECRET"
  access-token-expiration: 600000  # 10분 (밀리초)
  refresh-token-expiration: 1  # 1시간 (시간)
  
firebase:
  storage:
    bucket-name: "YOUR_BUCKET_NAME"
    json-path: "YOUR_JSON_PATH"
    
ai:
  flask-url: "YOUR_FLASK_URL"
  
google:
  api-key: "YOUR_API_KEY"
  google-korea-holiday-id: ko.south_korea#holiday@group.v.calendar.google.com
```


