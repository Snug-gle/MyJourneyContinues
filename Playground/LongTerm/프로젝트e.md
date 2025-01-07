### 1.  프로젝트 소개
- 테니스 코트 예약 애플리케이션
- 예약과 함께 필요시 매칭도 진행한다. 

### 2. 도메인

- **테니스장 예약 도메인**: `RallyPoint-Court
	- 주요 엔티티: `TennisCourt`, `Reservation`, `Schedule`
	- 주요 기능: 예약 확인, 예약 변경, 예약 취소
- **중고 직거래 서비스 도메인**: RallyPoint-Market`
	- 주요 엔티티: `Product`
	- 주요 기능: 상품 등록, 상품 조회, 거래 진행, 거래 이력 관리
- **매칭 서비스 도메인**: RallyPoint-Match`
	- 주요 엔티티: `Match`, GameType` (단식, 복식)
	- 주요 기능: 플레이어 매칭, 경기 유형 선택, 매칭 결과 저장(이벤트 대회 시에만)
- **회원 관리 도메인**: RallyPoint-User
	- 주요 엔티티: `User`, `Role`, `Authority`
	- 주요 기능: 사용자 등록, 로그인, 권한 관리, 사용자 정보 수정
	- 기타: admin, member, court_manager
- 공지사항 도메인: RallyPoint-Notice

### 3. stack
- MSA 아키텍쳐 
- Spring boot
- java 21, cotlin
- open feign
- webflux

### 4. init 정보
- gradle - kotlin

### 5. 개발 약속
- 요구사항 -> issue -> branch 생성
	- ex. 회원 가입
		- 이슈: 회원 가입 API
		- 브랜치 생성

### 6. 기능 요약
- 회원
	- 가입
	- 회원 정보 수정
- 로그인
	- 일반 로그인
	- OAuth2 로그인
	- jwt 인증
- 예약
	- 예약 현황 리스트
	- 예약 신청
