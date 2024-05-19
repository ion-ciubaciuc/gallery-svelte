<script lang="ts">
	export let src: string;
	export let alt: string | undefined = undefined;
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
<img
	class="size-full object-cover aspect-video max-md:h-20 rounded-xl"
	loading="lazy"
	{src}
	{alt}
	on:click
/>
