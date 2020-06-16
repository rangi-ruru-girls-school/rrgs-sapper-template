<script>
	import posts from './_posts.js'
</script>

<style>
</style>

<h1 class="title">Blog posts</h1>

{#each posts as post}
	<article class="section">
		<h2 class="title">{post.title}</h2>
		<p class="content">{@html post.html}</p>
	</article>
{/each}