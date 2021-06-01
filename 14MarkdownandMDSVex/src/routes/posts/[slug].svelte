<script context="module">
	export async function load({ page }) {
		const post = {
			title: page.params.slug,
			date: new Date(),
			body: 'lorem ipsum'
		};
		return {
			props: {
				post
			}
		};
	}
</script>

<script>
	import Hello from '../../posts/hello.md';

	export let post;
</script>

<Hello />

<h3>{post.title}</h3>
