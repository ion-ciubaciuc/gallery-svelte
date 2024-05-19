<script lang="ts">
	export let ref: HTMLDivElement | undefined;
</script>

<div
	class="size-full grid auto-cols-[100%] grid-flow-col overflow-x-auto sm:grid-cols-[repeat(auto-fill,100%)] snap-x snap-mandatory scroll-smooth motion-reduce:scroll-auto scrollbar-hidden gap-2 rounded-xl"
	bind:this={ref}
>
	<slot />
</div>
