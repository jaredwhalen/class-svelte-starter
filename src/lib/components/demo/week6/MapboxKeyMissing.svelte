<div class="missing">
	<h4 class="title">Mapbox access token required</h4>
	<p class="intro">These demos need a Mapbox public token. Without one, the map cannot load.</p>
	<ol class="steps">
		<li>
			Create a free account at
			<a href="https://account.mapbox.com/" target="_blank" rel="noopener noreferrer">mapbox.com</a>
		</li>
		<li>Copy your <strong>default public token</strong> from the Mapbox account dashboard</li>
		<li>Copy <code>.env.example</code> to <code>.env</code> in the project root</li>
		<li>
			Set <code>PUBLIC_MAPBOX_ACCESS_TOKEN=pk.your_token_here</code> in <code>.env</code>
		</li>
		<li>Restart the dev server: <code>npm run dev</code></li>
	</ol>
</div>

<style>
	.missing {
		display: flex;
		flex-direction: column;
		justify-content: center;
		min-height: 16rem;
		padding: 1.25rem 1.5rem;
		border: 1px dashed #d4a72c;
		border-radius: 0.5rem;
		background: #fffbeb;
		font-family: system-ui, sans-serif;
		color: #444;
	}

	.title {
		margin: 0 0 0.5rem;
		font-size: 1rem;
		font-weight: 600;
		color: #92400e;
	}

	.intro {
		margin: 0 0 1rem;
		line-height: 1.5;
	}

	.steps {
		margin: 0;
		padding-left: 1.25rem;
		line-height: 1.6;
	}

	.steps li + li {
		margin-top: 0.35rem;
	}

	code {
		font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
		font-size: 0.85em;
		background: rgba(0, 0, 0, 0.05);
		padding: 0.1em 0.35em;
		border-radius: 0.2rem;
	}

	a {
		color: #1d4ed8;
	}
</style>
