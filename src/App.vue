<template>
	<div id="app">
		<header class="hero is-medium is-primary is-bold">
			<div class="hero-body">
				<div class="container">
					<h1 class="title">My Vue App</h1>
					<h2 class="subtitle">Toggling layout using class binding</h2>
				</div>
			</div>
		</header>

		<tweet-container></tweet-container>
	</div>
</template>

<script>
import TweetContainer from "./components/tweet-container.vue";

export default {
	name: "App",
	components: {
		TweetContainer,
	},
};
</script>

<style>
#app {
	min-height: 100vh;
}
</style>
