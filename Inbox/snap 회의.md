1. 한 달에 한 번 오프라인 회의 필요하지 않나? , 진행사항 및 기술적인 부분에 대한 공유 희망
2. interfacer 프로토 타입 완료에 따른 공유
	1. 
	2. 새로운 모듈
	3. source - core - target(패키지 단으로 구분)
	4. moduleConfig -> new SpringApplicationBuilder(sourceClass) -> parent(core에 bean을 등록한 후 상속받기 위해 사용) -> run
	5. target - DBInsertModule --> @SnapInterfacerModule 애너테이션 사용 가능
	6. context 분리 필요 느낀 이유 -> restAPI, EAI, File등 사용 케이스 마다 다름
		```
		초기화 동작 시의 가지 수가 많음
		 ````
	6. 레거시 받아서 DB에 넣어줌.  고객의 레거시가 무엇이든 restAPI은 무조건 만들것. EAI는 금융권에서 무조건 만듬. 대용량 파일도 처리
	7. 프로세스가 죽었을 시.... 유실 방지가 요구 사항에 들어감 
	8. DB 고객이 fdb 함수를 만들어야 한다고 요구...  
	9. target 쪽이 비즈니스 로직이 있을 것(수신거부, 스팸 필터링 등)
	10. UMS 웹 템플릿....  템플릿ID 등 변수부만 보낼 수 있을 것... 치환해서 넣겠지.. UMS 핵심 기능들이며 위 개발 건들로 가능해질 것
	11. 성능 이슈...  극대화 방안....? 고객 인프라 환경에... Redis 추천해 줄수 있으나 자첵적으로는 캐싱 
	12. DB에서 메모리에 퍼올리면... 성능에 문제가 없을것...
