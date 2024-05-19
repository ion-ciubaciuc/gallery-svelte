<script lang="ts">
	import { Gallery } from '$lib';
	import '../app.css';

	const items = [
		{
			slide: { src: '/assets/picture_1.webp' },
			thumbnail: { src: '/assets/picture_1_thumbnail.webp' }
		},
		{
			slide: { src: '/assets/picture_2.webp' },
			thumbnail: { src: '/assets/picture_2_thumbnail.webp' }
		},
		{
			slide: { src: '/assets/picture_3.webp' },
			thumbnail: { src: '/assets/picture_3_thumbnail.webp' }
		},
		{
			slide: { src: '/assets/picture_4.webp' },
			thumbnail: { src: '/assets/picture_4_thumbnail.webp' }
		},
		{
			slide: { src: '/assets/picture_5.webp' },
			thumbnail: { src: '/assets/picture_5_thumbnail.webp' }
		}
	];
</script>

<svelte:head>
	<title>Svelte Gallery</title>
</svelte:head>

<div class="container mx-auto p-2">
	<Gallery {items} />
</div>
