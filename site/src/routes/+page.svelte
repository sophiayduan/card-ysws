<script lang="ts">
    import { Canvas } from '@threlte/core'
    import Scene from '$lib/components/Scene.svelte'
</script>
<section id="hero" class="w-screen min-h-screen bg-beige p-6 xl:p-14 grid grid-cols-1 grid-rows-1">
    <div class="col-start-1 row-start-1 grid grid-cols-1 grid-rows-1 place-items-center">
        <div class="opacity-40 col-start-1 row-start-1 z-0 relative">
            <!-- <Canvas>
                <Scene />
            </Canvas> -->
        </div>
        <nav class="col-start-1 row-start-1 z-10">
            <ul class="flex gap-2 text-beige font-medium ">
                <li class="bg-brown px-2 py-0.5 w-fit text-lg">ABOUT</li>
                <li class="bg-brown px-2 py-0.5 w-fit text-lg">GALLERY</li>
                <li class="bg-brown px-2 py-0.5 w-fit text-lg">CATEGORIES</li>
                <li class="bg-brown px-2 py-0.5 w-fit text-lg">EXAMPLES</li>
                <li class="bg-brown px-2 py-0.5 w-fit text-lg">CONTACT</li>
            </ul>
        </nav>




    </div>
    <div class="col-start-1 row-start-1 flex flex-col gap-4 w-full h-full z-10 relative text-brown">
        <h1 class="text-[18vh] leading-40 font-semibold text-purple font-bebas">LOREM IPSUM</h1>
        <p class="xl:max-w-md -mt-6 text-3xl">For teens 13-18. Begins September 10th.</p>
        <form class=" border border-brown rounded-xs bg-beige w-fit">
            <div class="h-14 min-w-60 lg:min-w-100 rounded-sm flex p-1.5">
                <input name="email" type="email" placeholder="johncena@hackclub.com" class="w-full px-4">
                <button class="ml-auto bg-green font-semibold text-3xl px-3 rounded-xs border border-brown font-bebas pt-0.5">RSVP</button>
            </div>
        </form>
        <div class="mt-auto w-full flex justify-between items-end">
            <h3 class="text-3xl xl:text-5xl max-w-lg lg:max-w-2xl font-medium opacity-80">A printed circuit board design competition for <span class="underline text-blue-700 font-medium">all skill levels</span></h3>
            <div class="w-100 h-60 border border-brown rounded-xs">
            </div>
        </div>
    </div>
</section>
