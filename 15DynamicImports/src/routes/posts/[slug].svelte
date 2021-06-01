<script context="module">
	export async function load({ page }) {
		const Hello = (await import(`../../posts/${page.params.slug}.md`)).default;

		// const post = {
		// 	title: page.params.slug,
		// 	date: new Date(),
		// 	body: 'lorem ipsum'
		// };
		return {
			props: {
				Hello
			}
		};
	}
</script>

<script>
	// import Hello from '../../posts/hello.md';
	export let Hello;
</script>

<Hello />
