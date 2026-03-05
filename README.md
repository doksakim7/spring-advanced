# SPRING ADVANCED

# 프로젝트 소개
이 프로젝트는 내일배움캠프 SPRING ADVANCED 강좌의 코드 개선 과제입니다.  
Spring Boot 기반의 3-Layer Architecture(Controller–Service–Repository)를 적용한 프로젝트에서  
발견된 오류를 단계별로 수정하고 코드 품질을 향상시키는 작업을 수행했습니다.  
주요 목표는 코드 리팩토링, 성능 개선, 테스트 코드 안정화입니다.


## 수행한 과제

### Lv.0 - 환경 설정 문제
- application.yml 미존재로 인한 DB, JWT Secret Key 에러 해결
- 로컬 환경에 맞게 설정 파일 생성 및 관리

### Lv.1 - ArgumentResolver
- AuthUserArgumentResolver 등록 문제 해결
- Controller에서 `@Auth AuthUser` 정상 주입 확인

### Lv.2 - 코드 품질 개선
- **Early Return** 적용 → 불필요한 `encode()` 제거
- **불필요한 if-else 제거** → Guard Clause 적용
- **Validation 책임 이동** → Service → DTO

### Lv.3 - N+1 문제 해결
- Todo 조회 시 N+1 문제 발생 → `@EntityGraph` 사용으로 해결
- Page<Todo> 조회에서도 User 연관 데이터 한 번에 로딩

### Lv.4 - 테스트 코드 개선
- PasswordEncoderTest, ManagerServiceTest, CommentServiceTest 수정
- null 체크 및 예외 타입/메시지 일치화
- 단위 테스트 정상 통과 확인


## 기술 스택
- Language: Java 17  
- Framework: Spring Boot  
- Persistence: Spring Data JPA + MySQL  
- Build Tool: Gradle  
- Environment: Web Application (REST API)


## 프로젝트 구조 (주요 패키지)
<img width="565" height="672" alt="스크린샷 2026-03-05 오후 7 40 52" src="https://github.com/user-attachments/assets/39e4337d-1314-4e66-b920-8a8a8acbf637" />


## 원본 출처 및 라이선스
이 프로젝트는 [f-api/spring-advanced](https://github.com/f-api/spring-advanced) 리포지토리를 포크하여 수정한 것입니다.  
MIT 라이선스는 본 리포지토리에서 이루어진 수정 및 추가 코드에 적용됩니다.  
원본 프로젝트의 저작권 및 라이선스는 원저작자에게 있습니다.


## ⚙️ application.yml 설정
보안상의 이유로 `application.yml` 파일은 GitHub에 포함되어 있지 않습니다.  
프로젝트 실행 전 아래 파일을 복사하여 사용해주세요.  
`src/main/resources/application-example.yml → src/main/resources/application.yml`  
복사 후 자신의 환경에 맞게 DB 정보 및 JWT 설정을 수정해주세요.  
※ application.yml은 .gitignore에 의해 관리됩니다.
