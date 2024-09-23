1. 부모[[ app.vue ]]에서 props 등록
	``` vue
	<product-modal :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>
	```
2. 자식[[ product-modal]] 은  props로 받은 것을 등록
	``` vue```