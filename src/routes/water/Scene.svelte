<script lang="ts">
	import { T } from '@threlte/core';
	import { OrbitControls, interactivity } from '@threlte/extras';
	import { spring } from 'svelte/motion';
	import Pool from './Pool.svelte';
	import Ball from './Ball.svelte';

	interactivity();

	const scale = spring(1);
</script>

<T.PerspectiveCamera
	makeDefault
	position={[10, 10, 10]}
	on:create={({ ref }) => {
		ref.lookAt(0, 0, 0);
	}}
>
	<OrbitControls />
</T.PerspectiveCamera>

<T.DirectionalLight position={[-7, 10, -3]} intensity={Math.PI} castShadow />

<T.AmbientLight intensity={0.3} />

<Pool />
<Ball />

<T.GridHelper args={[50]} cellColor="#487bfd" sectionColor="#487bfd" />
