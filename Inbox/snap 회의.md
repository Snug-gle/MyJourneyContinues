1. 한 달에 한 번 오프라인 회의 필요하지 않나? , 진행사항 및 기술적인 부분에 대한 공유 희망
2. interfacer 프로토 타입 완료에 따른 공유
	1. 배경
		1. 레거시 DB에 넣어줌... 혹은 DB to DB 모듈  고객의 레거시가 무엇이든 restAPI은 무조건 만들것. EAI는 금융권에서 무조건 만듬. 대용량 파일도 처리
		2. 프로세스가 죽었을 시.... 유실 방지가 요구 사항에 들어감 
		3. DB 고객이 fdb 함수를 만들어야 한다고 요구...  
		4. target 쪽이 비즈니스 로직이 있을 것(수신거부, 스팸 필터링 등)
		5. UMS 웹 템플릿....  템플릿ID 등 변수부만 보낼 수 있을 것... 치환해서 넣겠지.. UMS 핵심 기능들이며 위 개발 건들로 가능해질 것
		6. 성능 이슈...  극대화 방안....? 고객 인프라 환경에... Redis 추천해 줄수 있으나 자첵적으로는 캐싱 
		7. DB에서 메모리에 퍼올리면... 성능에 문제가 없을것...
	2. 구조
		1. 새로운 모듈
		2. source - core - target(패키지 단으로 구분)
		3. moduleConfig -> new SpringApplicationBuilder(sourceClass) -> parent(core에 bean을 등록한 후 상속받기 위해 사용) -> run
		4. target - DBInsertModule --> @SnapInterfacerModule 애너테이션 사용 가능
		5. context 분리 필요 느낀 이유 -> restAPI, EAI, File등 사용 케이스 마다 다름
		6. sourceQueue, targetQue는 하나로 구성해도 되지만 역할이나 성능등의 이유가 있고 더티 상태 유지를 위해 사용
		7. H2는 현재 디스크모드로  파일로 나오기에 조회가 가능함
		8. 병렬 타겟 DB insert 구조로 순서 보장에 대한 이슈 제기
			1. messageCheckService(snap), same-phone-delay-...
			2. snap.. 파일 큐(c라이브러리) 1번(클린), 2번(더티)인 케이스가 있어
			3. 그 때 앞 순번에 클린이 있으면  클린이 먼저 나와
			4. 스냅은 동보 기능 때문에 getList를 사용해야 함.. PersistenceTargetQue
			5. 허브는 프로젝트 단위로 중복체크 함
			6. 더티 상태에서 죽었을 시 더티 건을 읽음 그래서 문제가 없는 듯
			7. 동보 발송 중 실패하면... 모두 rollback 되야 하는데...
		9. core
			1. source - restapi
			2. 쓰레드 4개(패럴 = 4) 50건 씩(배치 사이즈 = 50)
			3. 50건 발송 시... 한 건에 문제가 있어 rollback 혹은 기타 조치가 필요한 경우 방어로직 필요하지 않나?
			4. 한 개 쓰레드로 단건 insert 처리 시... 초당 100건 내외...
			5. UMS는 보내줄 때  클라이언트키를 보내줌... 시퀀스하게 보내주지는 않음
3. 