<script lang="ts">
	export let direction: 'left' | 'right';
</script>

<button
	class="absolute bg-gray-600 bg-opacity-80 rounded-full text-white p-1 top-1/2 -translate-y-1/2"
	class:left-2={direction === 'left'}
	class:right-2={direction === 'right'}
	type="button"
	on:click
>
	<slot />
</button>
