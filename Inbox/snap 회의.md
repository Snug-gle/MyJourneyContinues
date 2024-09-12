1. 한 달에 한 번 오프라인 회의 필요하지 않나? , 진행사항 및 기술적인 부분에 대한 공유 희망
2. interfacer 프로토 타입 완료에 따른 공유
	1. 새로운 모듈
	2. source - core - target(패키지 단으로 구분)
	3. moduleConfig -> new SpringApplicationBuilder(sourceClass) -> parent(core에 bean을 등록한 후 상속받기 위해 사용) -> run
	4. target - DBInsertModule --> @SnapInterfacerModule 애너테이션 사용 가능
	5. context 분리 필요 느낀 이유 -> restAPI, EAI, File 등 
		```
		초기화 동작 시의 가지 수가 많음
		 ````

3. 개발 환경
4. tdd - 토비 영상 
5. 