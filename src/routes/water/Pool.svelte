<script lang="ts">
	import { T } from '@threlte/core';
	import { DoubleSide, FrontSide } from 'three';
</script>

<T.Group>
	<T.Mesh position.y={0.1} rotation.x={Math.PI / 2} receiveShadow castShadow>
		<T.PlaneGeometry args={[8, 8]} />
		<T.MeshStandardMaterial color="#dfdfdf" side={DoubleSide} />
	</T.Mesh>
	{#each Array(4) as _, i}
		<!-- Create 4 walls around the plane -->
		<T.Mesh
			position={[i % 2 ? (i === 1 ? 4 : -4) : 0, 2.1, i % 2 ? 0 : i === 0 ? 4 : -4]}
			rotation.y={i % 2 ? (i == 1 ? -Math.PI / 2 : Math.PI / 2) : i == 0 ? -Math.PI : 0}
			receiveShadow
			castShadow
		>
			<T.PlaneGeometry args={[8, 4]} />
			<T.MeshStandardMaterial color="#dfdfdf" side={FrontSide} />
		</T.Mesh>
	{/each}
</T.Group>
