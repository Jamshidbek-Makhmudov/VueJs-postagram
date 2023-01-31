<template>
	<div class="box text-center">
		<Login />
	</div>
</template>

<script>
import { Login } from '@/components'
export default {
	components: { Login },
}
</script>

<style scoped>
.box {

	border: none;
	border-radius: 8px;
	background: -webkit-linear-gradient(left, #7f049e, #f09f34);
	box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
