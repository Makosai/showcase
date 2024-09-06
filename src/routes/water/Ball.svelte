<script lang="ts">
	import { T } from '@threlte/core';
</script>

<T.Group>
	<T.Mesh position.y={1.25} receiveShadow castShadow>
		<T.SphereGeometry args={[1]} />
		<T.MeshStandardMaterial color="#487bfd" toneMapped={false} />
	</T.Mesh>
</T.Group>
