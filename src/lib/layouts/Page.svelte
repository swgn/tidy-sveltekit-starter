<script lang="ts">
	import { page } from '$app/state';

	const {
		data,
		title = 'Page Title',
		description = 'Page description',
		date,
		updated,
		children
	} = $props();
</script>

<svelte:head>
	<title>{title}</title>
	<meta property="og:title" content={title} />
	<meta property="og:url" content={String(page.url)} />
	<meta name="description" content={description} />
	<meta property="og:description" content={description} />
	<meta property="og:type" content="article" />
	<meta property="article:published_time" content={new Date(date).toISOString()} />
	<meta property="article:modified_time" content={new Date(updated ?? date).toISOString()} />
	<!-- {#if updated} -->
	<meta property="og:updated_time" content={new Date(updated ?? date).toISOString()} />
	<!-- {/if} -->
</svelte:head>

<h1>{title}</h1>
{@render children?.()}
<section class="not-prose my-6">
	<ul class="flex flex-row gap-1 font-mono">
		<li>Published: {new Date(date).toISOString().slice(0, 10)}</li>
		{#if updated}<li>— Updated: {new Date(date).toISOString().slice(0, 10)}</li>{/if}
	</ul>
</section>
