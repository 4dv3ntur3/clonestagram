# 인스타그램 클론 코딩

### 0. 개발 환경
- eclipse jee 2020-06
- java 1.8 (jdk, jre)
- spring boot 

### 1. 의존성
- (라이브러리 필요성 적어 두기)
- Spring Boot DevTools
- Lombok
- Spring Data JPA
- Spring Security
- Spring Web
- Oauth2


```xml
  <!-- 여기에 pom.xml에 추가한 dependency를 적나? -->
```

### 2. 데이터베이스
```mysql
여기다가 생성하는 코드를 쓰나...?
```

### 3. yml 설정
- yml...? 생성한 프로젝트 내의 기본 폴더에서는 안 보이는데 어디서 읽어와서 쓰는 거지 이참에 yml 파일에 대해서도 정리해 둘 것 
server:
  port: 8080 (나는 8090으로 했음)
  servlet:
    context-path: / (localhost:8080/ 이 home 화면이라는 설정?)
    encoding:
      charset: utf-8
      enabled: true

spring:
  mvc:
    view:
      prefix: /WEB-INF/views (이 폴더 밑에 view들이 있는 거고, 확장자는 jsp라는 뜻인가)
      suffix: .jsp
    
  datasource:
    (이 부분 주의하기!!! 내 DB에 맞게 해야 함. 그리고 공개적으로 작성할 건 아닌 듯... 그래서 yml 파일에 보관하나?)
    drive-class-name: com.mysql.jdbc.driver
    url: jdbc:mysql://localhost:3306/costa?serverTimezone=Asia/Seoul&useSSL=false&allowPublicKeyRetrieval=true
    username:
    password:
  
  jpa:
    open-in-view: true 컨트롤러가 끝날 때까지 세션이 유지
    hibernate:
      ddl-auto: create 할 때마다 DB 생성 (뭐지?? true 설정 같은 게 아닌가? false면 설정 안하나? 김영한 강의에 비슷한 내용 있었던 것 같으니 참고)
      naming: 네이밍 전략 방식 모델에 있는 그대로?
        physical-strategy: org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl
      show-sql: true 이것도 김영한 강의에 있었다
      
  servlet: 사진을 업로드할 때 max size
    multipart:
      enabled: true
      max-file-size: 2MB (졸프였나? 아니면 무인매대 플젝이었나...? node.js 할 때 본 것 같은데)
  
  security: 시큐리티 처음에 로그인 설정 user. 바꿀 수 있음
    user:
      name: test
      password: 1234
      
  file: 사진 업로드(배포) 시 경로 설정. 저장할 경로인가? 
    path: (프로젝트 경로에서 main/resources/upload/)
    
  dependency에서 버전에 컴파일 에러 나면 그냥 지우고 하기. 자동으로 맞춰준다.
        




     

