<script lang="ts">
  import { T } from '@threlte/core'
  import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js'
  import { useLoader } from '@threlte/core'
  import { GLTF, OrbitControls } from '@threlte/extras'

  const gltf = useLoader(GLTFLoader).load('src/lib/assets/card-example.gltf')
  // import { interactivity } from '@threlte/extras'
  // import { Spring } from 'svelte/motion'

</script>


{#if $gltf}

<T.PerspectiveCamera
    makeDefault
    position={[1, 4, 0]}
    up={[1, 0, 0]}
    <!-- lookAt.y={0.5} -->
    <!-- fov={25} -->
>
    <OrbitControls
        autoRotate
        enableDamping
        enableZoom={false}
        maxPolarAngle={1.4}
        minPolarAngle={1.6}
    />
</T.PerspectiveCamera>
<T.DirectionalLight position={[5, 10, 3]} intensity={1}/>
<T.AmbientLight intensity={1}/>
<T is={$gltf.scene} scale={0.09} rotation={[0, -0.45, 0]} position={[0, -0.05, 0]} />
{/if}

<!-- <T.PerspectiveCamera
    makeDefault
    position={[0, 0, 0]}
    fov={25}
>
    <OrbitControls
        autoRotate
        enableDamping
        enableZoom={false}
    />
</T.PerspectiveCamera>

<T.AmbientLight />
<GLTF url="src/lib/assets/card-example.gltf" /> -->

<!-- custom shape
<T.Mesh
    position.y={1}
    scale={3}
>
    <T.BoxGeometry args={[2.5, 3.5, 0.2]} />
    <T.MeshBasicMaterial color="#120942"/>
</T.Mesh> -->
