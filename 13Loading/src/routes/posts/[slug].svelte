<script context="module">
	// type LoadInput = {
	// 	page: {
	// 		host: string;
	// 		path: string;
	// 		params: Record<string, string | string[]>;
	// 		query: URLSearchParams;
	// 	};
	// 	fetch: (info: RequestInfo, init?: RequestInit) => Promise<Response>;
	// 	session: any;
	// 	context: Record<string, any>;
	// };

	// type LoadOutput = {
	// 	status?: number;
	// 	error?: Error;
	// 	redirect?: string;
	// 	props?: Record<string, any>;
	// 	context?: Record<string, any>;
	// 	maxage?: number;
	// };

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
	export let post;
</script>

<h3>{post.title}</h3>
