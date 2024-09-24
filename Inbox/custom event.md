부모에게서 받아온 props data를 자식에서 수정할 수 없다. (Read-only)
custom event: 부모의 데이터를 바꾸고 싶을 때 메세지를 보냄
$emit 함수: 부모에게 메세지 보낼 때 사용. (vue에서 사용하는 특별한 변수)
``` vue
<template>
	<div>
		<img :src="원룸.image" class="room-img">
		<h4>{{ 원룸.title }}</h4>
		<p>{{ 원룸.price }} 원</p>
</div>
</template>

```