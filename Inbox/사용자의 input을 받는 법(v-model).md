``` vue
<template>
<!-- 모달창 -->
<div class="black-bg" v-if="모달창열렸니 == true">
	<div class="white-bg">
		<img :src="원룸.image">
		<h4>{{ 원룸.title }}</h4>
		<p>{{ 원룸.content }}</p>
		<input @input="">
		<p> {{ month }}개월 선택함 : {{ 원룸.price * month }} 원</p>
		<button @click="closeProductModal">닫기</button>
	</div>
</div>
</template>
```