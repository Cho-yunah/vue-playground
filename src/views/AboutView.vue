<script lang="ts" setup>
import { ref } from 'vue';

const show = ref(false);
</script>

<template>
	<div class="about">
		<h1>This is an about page</h1>
		<ul>
			<li>$route.name: {{ $route.name }}</li>
			<li>$route.path: {{ $route.path }}</li>
		</ul>
		<!-- <button @click="$router.push('/')">home 으로 이동</button> -->
	</div>
	<div class="transitionBox">
		<button @click="show = !show">toggle</button>
		<Transition><p v-if="show">hello</p></Transition>
	</div>
</template>

<style type="scss">
.transitionBox {
	background-color: pink;
	margin: 10px;
	padding: 10px;
}
.v-enter-active,
.v-leave-active {
	transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
	opacity: 0;
}
@media (min-width: 1024px) {
	.about {
		min-height: 100vh;
		display: flex;
		align-items: center;
	}
}
</style>
