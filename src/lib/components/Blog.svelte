<script>
	import ExampleStory from './stories/ExampleStory.svelte';

	// Copy _StoryCardTemplate.svelte into stories/, rename it, then import here:
	// import YourNameStory from './stories/YourNameStory.svelte';
</script>

<main class="blog">
	<div class="blog-column">
		<header class="blog-header">
			<h1 class="blog-title">Blog title here</h1>
			<p class="blog-date">Published June 10, 2026</p>
		</header>

		<ExampleStory />
		<!-- <YourNameStory /> -->
	</div>
</main>

<style>
	.blog {
		min-height: 100vh;
		padding: 3rem 1.5rem 4rem;
		background: #fff;
		color: #111;
	}

	.blog-column {
		max-width: 42rem;
		margin: 0 auto;
	}

	.blog-header {
		margin-bottom: 3rem;
	}

	.blog-title {
		font-size: 2.25rem;
		font-weight: 700;
		line-height: 1.15;
		margin: 0 0 0.75rem;
	}

	.blog-date {
		font-size: 0.875rem;
		color: #666;
		margin: 0;
	}
</style>
