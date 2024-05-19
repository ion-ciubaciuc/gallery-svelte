<script lang="ts">
	export let src: string;
	export let alt: string | undefined = undefined;
</script>

<img
	class="object-cover size-full snap-center snap-always max-lg:aspect-video rounded-xl"
	loading="lazy"
	{src}
	{alt}
/>
