### 1. 도메인

- **테니스장 예약 도메인**: `RallyPoint-Court
	- 주요 엔티티: `TennisCourt`, `Reservation`, `Schedule`
	- 주요 기능: 예약 확인, 예약 변경, 예약 취소
- **중고 직거래 서비스 도메인**: RallyPoint-Market`
	- 주요 엔티티: `Product`, `Transaction`, `Se
	- 주요 기능: 상품 등록, 상품 조회, 거래 진행, 거래 이력 관리
- **매칭 서비스 도메인**: RallyPoint-Match`
	- 주요 엔티티: `Match`, `Player`, `GameType` (단식, 복식)
	- 주요 기능: 플레이어 매칭, 경기 유형 선택, 매칭 결과 저장
- **회원 관리 도메인**: RallyPoint-User
	- 주요 엔티티: `User`, `Role`, `Authority`
	- 주요 기능: 사용자 등록, 로그인, 권한 관리, 사용자 정보 수정
	- 기타: admin, member, guest

### 2. stack
데이터베이스 선택

- **테니스장 예약 도메인 (`CourtReservation`)**:
    - **관계형 데이터베이스** (예: MySQL, PostgreSQL)
    - 예약 시스템은 일정, 사용자 정보, 예약 상태와 같은 구조화된 데이터를 효율적으로 관리할 수 있는 관계형 데이터베이스가 적합합니다.
- **중고 직거래 서비스 도메인 (`Marketplace`)**:
    - **NoSQL 데이터베이스** (예: MongoDB, Cassandra)
    - 상품 데이터는 다양한 속성을 가질 수 있으며, 확장성과 유연한 데이터 모델링이 필요할 수 있기 때문에 NoSQL 데이터베이스가 적합할 수 있습니다.
- **매칭 서비스 도메인 (`Matchmaking`)**:
    - **인메모리 데이터베이스** (예: Redis)
    - 빠른 응답 속도가 필요한 매칭 로직 처리에는 인메모리 데이터베이스가 적합하며, 실시간 데이터 처리에 유리합니다.. 
- MSA 아키텍쳐 
- Spring boot
- java 21, cotlin
- open feign
- webflux