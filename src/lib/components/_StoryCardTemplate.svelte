<!--
  Copy this file into the stories/ folder, rename it (e.g. JaneStory.svelte),
  then import your new component in Blog.svelte.
-->

<article class="story-card">
	<hr class="divider" />

	<h2 class="headline">Your headline here</h2>
	<p class="byline">By Your Name</p>

	<p>Your first paragraph goes here.</p>
	<p>Your second paragraph goes here.</p>

	<figure class="chart">
		<figcaption class="chart-title">Chart title</figcaption>

		<div class="chart-workspace">
			<p class="chart-placeholder">Your chart goes here</p>
		</div>

		<figcaption class="chart-footer">Chart source or caption</figcaption>
	</figure>
</article>

<style>
	.story-card {
		margin-bottom: 3rem;
	}

	.divider {
		border: none;
		border-top: 1px solid #222;
		margin: 0 0 2rem;
	}

	.headline {
		font-size: 1.75rem;
		font-weight: 700;
		line-height: 1.2;
		margin: 0 0 0.5rem;
	}

	.byline {
		font-size: 0.875rem;
		color: #666;
		margin: 0 0 1.5rem;
	}

	p {
		font-size: 1.0625rem;
		line-height: 1.7;
		margin: 0 0 1rem;
	}

	.chart {
		margin: 2rem 0 0;
	}

	.chart-title {
		font-size: 0.875rem;
		font-weight: 600;
		margin-bottom: 0.75rem;
	}

	.chart-workspace {
		display: flex;
		align-items: center;
		justify-content: center;
		min-height: 320px;
		border: 1px solid #ddd;
		background: #fafafa;
	}

	.chart-placeholder {
		margin: 0;
		font-size: 0.875rem;
		color: #999;
	}

	.chart-footer {
		margin-top: 0.75rem;
		font-size: 0.8125rem;
		color: #666;
	}
</style>
