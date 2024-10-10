``` vue
<template>
<!-- 모달창 -->
<div class="black-bg" v-if="모달창열렸니 == true">
	<div class="white-bg">
		<img :src="원룸.image">
		<h4>{{ 원룸.title }}</h4>
		<p>{{ 원룸.content }}</p>
		<input @input="month = $event.target.value">
		<p> {{ month }}개월 선택함 : {{ 원룸.price * month }} 원</p>
		<button @click="closeProductModal">닫기</button>
	</div>
</div>
</template>
<script>
	export default {
		name : 'ProductModal',
		data() {
		return {
		month : 1,
		}
		},
		props : {
		원룸 : Object,
		모달창열렸니 : Boolean,
		누른거 : Number
		},
		methods : {
		closeProductModal() {
		console.log("[product-modal.vue]모달창열렸니: " + this.모달창열렸니)
		this.$emit('closeModal', this.원룸.id)
		}
		}
	}
</script>
```