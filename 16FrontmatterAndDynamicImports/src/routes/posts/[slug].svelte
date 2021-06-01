<script context="module">
	export async function load({ page }) {
		const Hello = await import(`../../posts/${page.params.slug}.md`);
		return {
			props: {
				Hello: Hello.default,
				title: Hello.metadata.title
			}
		};
	}
</script>

<script>
	export let Hello;
	export let title;
</script>

<h2>{title}</h2>

<Hello />
