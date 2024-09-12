1. 한 달에 한 번 오프라인 회의 필요하지 않나? , 진행사항 및 기술적인 부분에 대한 공유 희망
2. interfacer 프로토 타입 완료에 따른 공유
	1. 새로운 모듈
	2. source - core - target(패키지 단으로 구분)
	3. moduleConfig -> new SpringApplicationBuilder(sourceClass) -> parent(core에 bean을 등록한 후 상속받기 위해 사용) -> run
	4. target - DBInsertModule --> @SnapInterfacerModule 애너테이션 사용 가능
	5. context 분리 필요 느낀 이유 -> restAPI, EAI, File등 사용 케이스 마다 다름
		```
		초기화 동작 시의 가지 수가 많음
		 ````
	6. 레거시 받아서 DB에 넣어줌.  고객의 레거시가 무엇이든 restAPI은 무조건 만들것. EAI는 금융권에서 무조건 만듬. 대용량 파일도 처리
	7. 
