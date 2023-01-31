<template>
	<div class="box text-center d-flex flex-column flex-md-row align-items-center py-3 mb-4 border-bottom">
		<a href="/">
			<img src="../assets/logo/sec2__logo.png" alt="logo" class=" w-50 cursor:pointer" @click="toHomeHandler" />
		</a>


		<nav class=" d-inline-flex mt-2 mt-md-0 ms-md-auto">
			<template v-if="isLoggedIn">
				<RouterLink :to="{ name: 'create-article' }" class="btn me-3 py-2 text-dark text-decoration-none">Create article
				</RouterLink>
				<RouterLink :to="{ name: 'home' }" class="btn me-3 py-2 text-dark text-decoration-none">{{
					currentUser.username
				}}</RouterLink>
				<a href="#" class="btn me-3 py-2 text-dark text-decoration-none" @click="logout">Logout</a>
			</template>

			<template v-if="isAnonymous">
				<RouterLink class="btn me-3 py-2 text-dark text-decoration-none cursor:pointer" :to="{ name: 'login' }">
					Login
				</RouterLink>

				<RouterLink class="btn me-3 py-2 text-dark text-decoration-none cursor:pointer" :to="{ name: 'register' }">
					Register
				</RouterLink>
			</template>
		</nav>
	</div>
</template>

<script>
import { mapGetters } from 'vuex'
import { logo } from '../contstants'
import { gettersTypes } from '@/modules/types'
export default {
	data() {
		return {
			logo,
		}
	},
	computed: {
		...mapGetters({
			currentUser: gettersTypes.currentUser,
			isLoggedIn: gettersTypes.isLoggedIn,
			isAnonymous: gettersTypes.isAnonymous,
		}),
	},
	methods: {
		toHomeHandler() {
			return this.$router.push({ name: 'home' })
		},
		logout() {
			return this.$store.dispatch('logout')
		},
	},
}
</script>

<style scoped>
.nav {
	display: flex;
	align-items: center;
	justify-content: center;
}

.box {
	background: -webkit-linear-gradient(left, #626eda, #88b7ec);

	box-shadow: 15px 15px 15px rgba(0, 0, 0, 0.15);
}

.btn {
	cursor: pointer;
	font-size: large;
}

.btn:hover {
	opacity: 0.7;
	border-bottom: 1px solid blue;
}
</style>
