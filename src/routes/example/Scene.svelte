<script lang="ts">
    import { T } from '@threlte/core'
    import { Grid, OrbitControls, interactivity } from '@threlte/extras'
    import { spring } from 'svelte/motion'
  
    interactivity()
  
    const scale = spring(1)
  </script>
  
  <T.PerspectiveCamera
    makeDefault
    position={[10, 10, 10]}
    on:create={({ ref }) => {
      ref.lookAt(0, 0, 0)
    }}
  >
    <OrbitControls />
  </T.PerspectiveCamera>
  
  <T.DirectionalLight
    position={[3, 10, 7]}
    intensity={Math.PI}
  />
  
  <T.AmbientLight intensity={0.3} />
  
  <T.Group
    scale={$scale}
    on:pointerenter={() => scale.set(1.5)}
    on:pointerleave={() => scale.set(1)}
    on:click={() => scale.set(0.5)}
  >
    <T.Mesh position.y={1}>
      <T.SphereGeometry args={[1]} />
      <T.MeshStandardMaterial
        color="#487bfd"
        toneMapped={false}
      />
    </T.Mesh>
  </T.Group>
  
  <Grid
    cellColor="#487bfd"
    sectionColor="#487bfd"
  />
  