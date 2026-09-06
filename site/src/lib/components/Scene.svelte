<script lang="ts">
  import { T } from '@threlte/core'
  import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js'
  import { interactivity, useCursor } from '@threlte/extras'
  import { useLoader } from '@threlte/core'
  import { GLTF, OrbitControls } from '@threlte/extras'
  import { Spring } from 'svelte/motion'
  const scale = new Spring(0.18)
  import * as THREE from 'three'

  const gltf = useLoader(GLTFLoader).load('src/lib/assets/card-example.gltf')
  const { onPointerEnter, onPointerLeave } = useCursor()

  const loader = new THREE.AnimationLoader();
  interactivity()

</script>


{#if $gltf}

<T.PerspectiveCamera
    makeDefault
    position={[1, 2, 0]}
    up={[1, 0, 0]}
    <!-- lookAt.y={0.5} -->
    <!-- fov={25} -->
>
    <OrbitControls
        autoRotate
        autoRotateSpeed={1.5}
        enableDamping
        enableZoom={false}
        maxPolarAngle={1.4}
        minPolarAngle={1.6}

    />
</T.PerspectiveCamera>
<T.DirectionalLight position={[5, 10, 3]} intensity={1}/>
<T.AmbientLight intensity={1}/>
<T is={$gltf.scene}
    scale={scale.current}

    onclick={() => {
      window.open("/custom", "_self");

    }}
    onpointerenter={() => {
      onPointerEnter()
      scale.target = 0.19
    }}
    onpointerleave={() => {
      onPointerLeave()
      scale.target = 0.18
    }}
    rotation={[0, -0.45, 0]}
    position={[0, -0.05, 0]}


    />
{/if}
