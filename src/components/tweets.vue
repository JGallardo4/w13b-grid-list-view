<template>
	<section>
		<article class="media tweet" v-for="(tweet, index) in tweets" :key="index">
			<figure class="media-left">
				<p class="image is-64x64">
					<img src="https://bulma.io/images/placeholders/128x128.png" />
				</p>
			</figure>
			<div class="media-content">
				<div class="content">
					<p>
						<strong class="tweet__author">{{ tweet.author }}</strong>
						<small>@{{ tweet.author.toLowerCase() }}</small>

						<br />
						{{ tweet.content }}
					</p>
				</div>
			</div>
			<div class="media-right">
				<small class="tweet__date">{{ tweet.date }}</small>
			</div>
		</article>
	</section>
</template>

<script>
export default {
	name: "tweets",

	methods: {
		toggleView() {
			this.listView = !this.listView;
			console.log(!this.listView);
		},
	},

	data() {
		return {
			tweets: [
				{
					author: "Harry",
					content: "I want the nimbus 3000",
					date: "October 10, 2001 ",
				},
				{
					author: "Ron",
					content: "I hate spiders!",
					date: "October 20, 2001 ",
				},
				{
					author: "Hermione",
					content: "You're gonna get us killed, or worse... expelled",
					date: "October 05, 2001 ",
				},
			],
		};
	},
};
</script>

<style lang="scss" scoped>
.tweet {
	margin-top: 0 !important;
	padding-top: 0 !important;
}
</style>