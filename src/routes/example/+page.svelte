<script lang="ts">
	import { Canvas } from '@threlte/core';
	import Scene from './Scene.svelte';
</script>

<div class="wrapper">
	<Canvas>
		<Scene />
	</Canvas>

	<div class="description">
		<p>
			<strong>Click and drag</strong> to rotate the camera.
		</p>
		<p>
			<strong>Hover</strong> over the sphere to scale it up.
		</p>
		<p>
			<strong>Click the sphere</strong> to shrink it.
		</p>
	</div>
</div>

<style lang="postcss">
	div.wrapper {
		@apply h-full;
	}

	div.description {
		@apply absolute bottom-3 left-3 z-10 text-[#487bfd];
	}
</style>
