<template>
	<div>About</div>
	<button @click="linkTo">Home</button>
</template>

<script>
import { useRouter } from 'vue-router'
import axios from '../utils/axios'

export default {
	name: 'about-view',
	setup() {
		const router = useRouter()
		const linkTo = () => {
			router.push({
				path: '/home'
			})
		}
		axios
			.get('/users/XPoet')
			.then((res) => {
				console.log('res: ', res)
			})
			.catch((err) => {
				console.log('err: ', err)
			})

		return {
			linkTo
		}
	}
}
</script>
