# 고은지 (Elin)

**Node.js · NestJS 기반 백엔드 개발 14년차.** 정산·결제·라이선스처럼 데이터 정확성이 중요한 영역을 주로 다뤄왔습니다.

정산 도메인을 0부터 설계해 운영까지 책임졌습니다. 이후 결제와 정산을 별도 서비스로 나눈 분산 정산 구조로 발전시켰습니다. 대용량 조회 구조 개선, 비동기 처리, 장애 근본 원인 추적이 주력입니다. 화려한 단발성 성과보다 오래 함께 일하며 조직을 안정적으로 받치는 쪽에 가깝습니다.

- 📧 einee214@gmail.com
- 🔗 github.com/ein214
- 📄 **Portfolio** — https://ein214.github.io/portfolio/

---

## What I do

- **정산/결제 도메인** — 금융성 정확성(원 단위 정수 연산·불변성·감사추적)을 핵심 요구사항으로 둔 정산 시스템 설계
- **대용량 데이터 / 아키텍처** — 천만 건 규모 조회 구조 개선, CQRS·비정규화, SQS 기반 비동기 파이프라인
- **트러블슈팅 / 안정화** — 메모리 누수·큐 병목 등 장애의 근본 원인을 끝까지 추적
- **14년차 시니어 전반** — 운영 자동화, 점진적 마이그레이션, 백오피스 공통화로 조직 생산성 개선

---

## 대표 문제 해결 경험

### [정산 플랫폼 0→1 설계](https://github.com/ein214/portfolio/blob/main/troubleshooting/settlement-system-zero-to-one.md)
수동 엑셀 정산을 기획자 1명과 0부터 설계·구현했습니다. 출판사·저자가 얽힌 1:N 수익 분배와 이용권 일할 정산을 데이터 모델로 풀고 정산 오류를 코드화해 운영자가 직접 보정하는 자가복구 구조까지 만들었습니다.

### [천만 건 정산 조회 개선](https://github.com/ein214/portfolio/blob/main/troubleshooting/settlement-query-optimization.md)
정산 800만 건 규모에서 한 달 조회가 19초까지 걸렸습니다. 인덱스·파티셔닝으로 풀리지 않아 문제를 쿼리에서 데이터 모델로 옮겨 조회 전용 Flat Table과 큐 동기화로 읽기 경로를 분리했습니다(CQRS).

### [Bull Queue 처리 지연 장애](https://github.com/ein214/portfolio/blob/main/troubleshooting/bull-queue-bottleneck.md)
개별 작업은 1~5초인데 사용자 대기가 31분까지 늘었습니다. "느린 작업"과 "밀린 큐"를 구분해 concurrency 미설정이 원인임을 짚고 멱등성·graceful shutdown·오토스케일링까지 큐 운영 전반을 정비했습니다.

### [Node.js 워커 RSS 메모리 누수 추적](https://github.com/ein214/portfolio/blob/main/troubleshooting/redis-job-memory-leak.md)
워커 RSS가 시간당 수백 MB씩 늘다 `spawn ENOMEM`으로 죽는 문제였습니다. heap은 정상인데 RSS만 오르는 상황에서 가설을 차례로 기각해 네이티브 라이브러리의 메모리 미반환을 원인으로 특정했고 교체 후 메모리 사용률을 약 40%에서 7% 수준으로 낮췄습니다.

### [백오피스 공통화 — ListBuilder](https://ein214.github.io/portfolio/listbuilder/)
리스트 페이지마다 반복되던 조회·필터·정렬·엑셀 로직을 설정 객체 하나로 선언하는 재사용 빌더로 공통화했습니다. 관리자 페이지 10여 곳이 채택했습니다.

각 경험의 상세 — 문제 정의, 가설 기각 과정, 의사결정 근거 — 는 포트폴리오에 정리했습니다.
→ **[Portfolio](https://ein214.github.io/portfolio/)** (전체) · **[정산 시스템 Deep Dive](https://ein214.github.io/portfolio/settlement.html)** · **[ListBuilder Deep Dive](https://ein214.github.io/portfolio/listbuilder/)**

---

## 경력 요약

**(주)북아이피스** · Backend Developer · 2022.05 ~ 재직 중\
정산 시스템 0→1 설계·구축(SQS 기반 비동기 정산·1:N 저작권 분배·일할 정산), 정산 조회 전용 Read DB(CQRS) 구축, 저자 라이선스·정산 시스템 개편, Redis Job 메모리 누수 안정화, Watermark Queue 처리량·모니터링 개선, Express→NestJS 점진적 전환, AdminJS 기반 운영 도구 공통화.

**(주)유니윌 / 위즈페이** · 2020.07 ~ 2022.04\
온라인 교육 플랫폼 개발·운영, 정산 시스템 개발, AWS 환경 운영.

**주식회사 큐브시스템** · 2018.04 ~ 2020.06\
블록체인 월렛 서비스 및 API 개발, Laravel 기반 배치·정산 시스템 개발.

**(주)이비즈네트웍스** · 2013.03 ~ 2017.11\
여행 플랫폼·관리자 시스템 개발, 외부 제휴 REST API, 검색 성능 개선.

*초기 경력(2011~2012, 웹 퍼블리싱·유지보수) 포함 총 14년 2개월.*

---

## 기술 스택

**Backend** Node.js · NestJS · TypeScript · PHP · Laravel\
**Database** PostgreSQL · MySQL · Redis\
**Infra** AWS (Beanstalk · SQS · S3 · CloudWatch)

