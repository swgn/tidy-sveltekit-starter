<script>
	import { FOOTER_LINKS, SITE_TITLE } from '$lib/constants';
</script>

<section class="bg-ink/10 mt-12 flex flex-col gap-12 p-6 sm:flex-row sm:rounded-lg">
	<div>
		<a href="/" class="font-semibold">{SITE_TITLE}</a>
	</div>
	{#each FOOTER_LINKS as { group, links }}
		<ul class="flex flex-grow flex-col gap-2">
			<li><h4 class="font-semibold">{group}</h4></li>
			{#each links as { label, href }}
				<li><a {href}>{label}</a></li>
			{/each}
		</ul>
	{/each}
</section>
