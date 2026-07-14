# DejaVu 

개발자 채용공고를 분석하고, 이력서와 비교해 지원 준비를 돕는 서비스입니다.

## 프로젝트 이름

### DejaVu

개발자 채용공고를 더 쉽게 읽고 내 이력서에 무엇을 보완해야 하는지 확인할 수 있도록 돕는 프로젝트입니다.

## 사용한 기술

### Backend

- Java 17
- Spring Boot 4.0.7
- Spring Data JPA
- Spring Security
- Spring Validation
- React.js

### Database / Infra

- MariaDB
- Docker Compose
- Gradle

### API / Docs

- Swagger(OpenAPI)
- REST API

### AI / Feature

- OpenAI API 연동 구조
- 공고-이력서 키워드 비교 기능
- 공고 AI 분석 기능

## 실행 화면

추후 실행 화면 이미지 또는 GIF를 삽입할 예정입니다.

예시:

```md
![메인 화면](./docs/images/main.png)
![서비스 실행 화면](./docs/images/demo.gif)
```

## 실행 방법

### 1. 프로젝트 클론

```bash
git clone https://github.com/inspire-jobzip/backend.git
cd backend
```

### 2. 환경변수 파일 생성

```bash
cp .env.example .env
```

### 3. 데이터베이스 실행

Docker Compose 사용:

```bash
cd mariadb-setup
docker compose up -d
cd ..
```

직접 MariaDB를 세팅하는 경우:

```bash
mysql -u root -p < mariadb-setup/01_schema.sql
mysql -u root -p < mariadb-setup/02_seed_skills.sql
mysql -u root -p < mariadb-setup/03_sample_data.sql
mysql -u root -p < mariadb-setup/05_sample_saramin_job_notices.sql
```

### 4. 서버 실행

```bash
./gradlew bootRun
```

### 5. 테스트 실행

```bash
./gradlew test
```

### 6. 문서 확인

- Swagger UI: `http://localhost:8080/swagger-ui.html`
- OpenAPI Docs: `http://localhost:8080/api-docs`

## 만든 이유, 목표

채용공고는 정보가 많고 표현도 제각각이라, 지원자가 짧은 시간 안에 공고의 핵심 기술과 준비 방향을 파악하기 어렵다는 문제를 느껴 이 프로젝트를 만들었습니다.

DejaVu의 목표는 단순히 공고를 보여주는 데서 끝나지 않고, 공고 분석, 스크랩, 마감 일정 관리, 이력서 비교까지 이어지는 흐름을 제공하는 것입니다.

이 프로젝트를 통해 아래 내용을 배우고 구현하는 것을 목표로 했습니다.

- Spring Boot 기반 REST API 설계
- JWT 인증/인가 처리
- MariaDB 기반 데이터 모델링
- 채용공고와 이력서 데이터를 연결한 서비스 설계
- AI 기능을 실제 서비스 흐름에 연결하는 방법

## 만든 사람

- 김나연 
- 정세빈 
- 임현  
- 홍정현 

## 참고 문서

- [`docs/api/api-spec.md`](docs/api/api-spec.md)
- [`docs/database/erd-plan.md`](docs/database/erd-plan.md)
- [`docs/database/ddl.sql`](docs/database/ddl.sql)
- [`mariadb-setup/README.md`](mariadb-setup/README.md)
