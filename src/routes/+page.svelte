
<script>
	import { confetti } from '@neoconfetti/svelte';
	import { tick } from 'svelte'
	
	let x, y;
	let isVisible = false;

	const handleClick = async e => {
		x = e.clientX;
		y = e.clientY - 130;
		
		isVisible = false;
		await tick();
		isVisible = true
	}

	import cpuCategory from '$lib/assets/images/category/category-CPU.jpg';
	import videoCardCategory from '$lib/assets/images/category/category-VideoCard.jpg';
	import motherBoardCategory from '$lib/assets/images/category/category-MotherBoard.jpg';
	import storageCategory from '$lib/assets/images/category/category-Storage.jpg';
</script>

<svelte:body on:click={handleClick} />

{#if isVisible}
  <div style={`transform: translate(${x}px, ${y}px)`} use:confetti/>
{/if}

<!-- banner -->
<div class="bg-cover bg-no-repeat bg-center py-28 banner">
	<div class="container mx-auto flex flex-col justify-center text-center">
		<h1 class="text-6xl text-white font-medium mb-4 capitalize">
			best collection for <br> computer hardware
		</h1>
<!-- 		<p class="text-2xl text-white">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Aperiam <br>
			accusantium perspiciatis, sapiente
			magni eos dolorum ex quos dolores odio</p> -->


		<div class="mt-12">
			<a href="/" class="btn btn-primary btn-lg px-12">Shop Now</a>
		</div>
	</div>
</div>

<!-- categories -->
<!-- <div class="container py-16 m-auto">
	<h2 class="text-2xl font-medium text-gray-800 uppercase mb-6">shop by category</h2>
	<div class="grid grid-cols-3 gap-3">
		<div class="relative rounded-sm overflow-hidden group cpu-category">
			<img src={cpuCategory} alt="category 1" class="object-cover h-full">
			<a href="/shop?selectcat=1"
				class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center text-xl text-white font-roboto font-medium group-hover:bg-opacity-60 transition">CPU</a>
		</div>
		<div class="relative rounded-sm overflow-hidden group">
			<img src={videoCardCategory} alt="category 1" class="object-cover h-full">
			<a href="/shop?selectcat=2"
				class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center text-xl text-white font-roboto font-medium group-hover:bg-opacity-60 transition">Video card</a>
		</div>
		<div class="relative rounded-sm overflow-hidden group">
			<img src={motherBoardCategory} alt="category 1" class="object-cover h-full">
			<a href="/shop?selectcat=4"
				class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center text-xl text-white font-roboto font-medium group-hover:bg-opacity-60 transition">Mother board
			</a>
		</div>
		<div class="relative rounded-sm overflow-hidden group">
			<img src={storageCategory} alt="category 1" class="object-cover h-full">
			<a href="/shop?selectcat=5"
				class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center text-xl text-white font-roboto font-medium group-hover:bg-opacity-60 transition">Storage</a>
		</div>
		
	</div>
</div> -->

<style>
	/* :global(html) {
		background-color: theme(colors.gray.100);
	} */

	.banner {
		background-image: url($lib/assets/hardware_banner.jpg);
	}

	.movable {
		transition: transform 0.3s ease-in-out;
	}
</style>
