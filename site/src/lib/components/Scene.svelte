<script>
  import { T } from '@threlte/core'
  // import { interactivity } from '@threlte/extras'
  // import { Spring } from 'svelte/motion'

  // interactivity()
  // const scale = new Spring(1)
</script>

<T.PerspectiveCamera
    makeDefault
    position={[6, -4, -10]}
    oncreate={(ref) => {
      ref.lookAt(0, 1, 0)
    }}
/>

<T.Mesh
    position.y={1}
    scale={3}
>
    <T.BoxGeometry args={[2.5, 3.5, 0.2]} />
    <T.MeshBasicMaterial color="#120942"/>
</T.Mesh>
