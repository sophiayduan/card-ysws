<script lang="ts">
  import { T } from '@threlte/core'
  import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js'
  import { interactivity, useCursor } from '@threlte/extras'
  import { useLoader } from '@threlte/core'
  import { GLTF, OrbitControls, useGltf } from '@threlte/extras'
  import { Spring } from 'svelte/motion'
  import * as THREE from 'three'

  const models = [
    'models/card-example.glb',
    'models/card-example-2.glb',
    'models/card-example-3.glb',
    'models/card-example-4.glb',
  ]

  let currentCard = $state(0)
  const scale = new Spring(0.018)
  const { onPointerEnter, onPointerLeave } = useCursor()

  let gltf = $derived(useGltf(models[currentCard]))

  export function next() {
    currentCard = (currentCard + 1) % models.length
  }

  export function prev() {
    currentCard = (currentCard - 1 + models.length) % models.length
  }

  interactivity()
</script>


{#if $gltf}

<T.PerspectiveCamera
    makeDefault
    position={[1, 2, 0]}
    up={[1, 0, 0]}
>
    <!-- lookAt.y={0.5} -->
    <!-- fov={25} -->
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
    {#key currentCard}
        <T is={$gltf.scene}
            scale={scale.current}

            onclick={() => {
            window.open("/custom", "_self");

            }}
            onpointerenter={() => {
            onPointerEnter()
            scale.target = 0.019
            }}
            onpointerleave={() => {
            onPointerLeave()
            scale.target = 0.018
            }}
            rotation={[1, -0.0, 1]}
            position={[0, -0.05, 0]}

        />
    {/key}
{/if}
