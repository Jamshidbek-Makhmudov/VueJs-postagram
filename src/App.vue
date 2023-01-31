<template>
	<div class="out">
		<div class="">
			<Navbar />
			<div class=" container">
				<RouterView />
			</div>
		</div>
	</div>
</template>

<script>

import { Navbar } from '@/components'
import { RouterView } from 'vue-router'
export default {
	components: { Navbar },
	mounted() {
		this.$store.dispatch('getUser')
	},
}
</script>

<style scoped>
.out {
	background: whitesmoke;

	box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}
</style>
