<script>
	import { HEADER_LINKS, SITE_TITLE } from '$lib/constants';
</script>

<section class="bg-ink/10 mb-6 flex flex-row p-6 sm:rounded-lg">
	<a href="/" class="font-semibold">{SITE_TITLE}</a>
	<ul class="flex flex-grow flex-row justify-end gap-2">
		{#each HEADER_LINKS as { label, href }}
			<li><a {href}>{label}</a></li>
		{/each}
	</ul>
</section>
