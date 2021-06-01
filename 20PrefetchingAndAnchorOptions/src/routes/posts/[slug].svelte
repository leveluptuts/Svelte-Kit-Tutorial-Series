<script context="module">
	export async function load({ page }) {
		try {
			const Post = await import(`../../posts/${page.params.slug}.md`);

			return {
				// Data passed into svelte component
				props: {
					Post: Post.default
				}
			};
		} catch (e) {
			// https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
			// Redirect Example
			// return {
			// 	status: 307,
			// 	redirect: '/posts'
			// };
			// For status to work
			// We need the correct outputs
			// 404 needs error message
			// Redirects needs status and redirect
			return {
				status: 404,
				error: 'Post not found'
			};
		}
	}
</script>

<script>
	export let Post;
</script>

<Post />
