<script lang="ts">
	import ArrowLeft from './ArrowLeft.svelte';
	import ArrowRight from './ArrowRight.svelte';
	import Navigation from './Navigation.svelte';
	import Slide from './Slide.svelte';
	import Slider from './Slider.svelte';
	import Thumbnail from './Thumbnail.svelte';
	import { mod } from './utils';

	export let items: {
		slide: { src: string; alt?: string };
		thumbnail: { src: string; alt?: string };
	}[];

	let sliderRef: HTMLDivElement | undefined = undefined;
	let currentIndex = 0;

	const handleClick = (index: number) => {
		currentIndex = mod(index, items.length);
		sliderRef?.scrollTo({
			left: sliderRef.clientWidth * currentIndex
		});
	};

	const handleResize = () => {
		sliderRef?.scroll({
			left: sliderRef.clientWidth * currentIndex
		});
	};
</script>

<svelte:window on:resize={handleResize} />

<div
	class="flex flex-col-reverse md:grid grid-cols-5 h-full w-full overflow-hidden md:aspect-video gap-2"
>
	<div
		class="md:col-span-1 max-md:overflow-x-auto md:overflow-y-auto scrollbar-hidden gap-2 flex md:flex-col"
	>
		{#each items as item, i (i)}
			<Thumbnail {...item.thumbnail} on:click={() => handleClick(i)} />
		{/each}
	</div>
	<div class="md:col-span-4 relative">
		<Slider bind:ref={sliderRef}>
			{#each items as item, i (i)}
				<Slide {...item.slide} />
			{/each}
		</Slider>
		<Navigation direction="left" on:click={() => handleClick(currentIndex - 1)}>
			<ArrowLeft />
		</Navigation>
		<Navigation direction="right" on:click={() => handleClick(currentIndex + 1)}>
			<ArrowRight />
		</Navigation>
	</div>
</div>
