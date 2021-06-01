<script context="module">
	export async function load() {
		const posts = import.meta.globEager('../../posts/*.md');
		const postsList = Object.values(posts);
		const postsMeta = postsList.map((post) => {
			return post.metadata;
		});
		return {
			props: {
				posts: postsMeta
			}
		};
	}
</script>

<script>
	export let posts;
</script>

<div>
	<slot />
	<aside>
		<h5>Archive</h5>
		<ui>
			{#each posts as post}
				<li><a sveltekit:prefetch href={`/posts/${post.slug}`}>{post.title}</a></li>
			{/each}
			<li><a rel="external" href="https://leveluptutorials.com">Leve up</a></li>
		</ui>
	</aside>
</div>
