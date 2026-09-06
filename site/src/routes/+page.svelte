 <script lang="ts">
    import { Canvas } from '@threlte/core'
    import Scene from '$lib/components/Scene.svelte'
    import Navbar from '$lib/components/Navbar.svelte'
    import Footer from '$lib/components/Footer.svelte'
    import { onMount } from 'svelte';

    import { gsap } from 'gsap'

    let dateTime = new Date()

    // onMount(() => {
    //   gsap.registerPlugin(SplitText);
    //   const rsvp = document.querySelector<HTMLElement>('.rsvp');
    //   if (!rsvp) return

    //   const split = SplitText.create('.rsvp', { type: "chars" });

    //   const animation = gsap.from(split.chars, {
    //     duration:1,
    //     x:-50,
    //     ease:'power2.out',
    //     paused: true
    //   });
    //   const onEnter = () => animation.play()
    //   const onLeave = () => animation.reverse()
    //   rsvp.addEventListener('mouseenter', onEnter)
    //   rsvp.addEventListener('mouseleave', onLeave)

    //   return () => {
    //         rsvp.removeEventListener('mouseenter', onEnter)
    //         rsvp.removeEventListener('mouseleave', onLeave)
    //         split.revert()
    //         animation.kill()
    //       }

    // })





</script>
<section id="hero" class="noise w-screen min-h-screen p-6 bg-beige xl:p-14 grid grid-cols-1 grid-rows-1">
    <div class="absolute inset-0 bg-[url('../lib/assets/noise.gif')] opacity-14">

    </div>
    <a href="/custom" target="" class="z-100 mix-blend-multiply fixed top-1/2 left-0 -translate-y-1/2 w-12 h-40 hover:w-14 transition-all ease-in-out duration-300 bg-red text-red">
        <!-- <p class="-rotate-90 whitespace-nowrap translate-y-20 font-semibold text-white">View More</p> -->.
    </a>
    <div class="col-start-1 row-start-1 grid grid-cols-1 grid-rows-1 place-items-center h-full w-full">
        <div class="col-start-1 row-start-1 z-0 relative h-200 w-200">
            <Canvas>
                <Scene />
            </Canvas>
        </div>
        <Navbar />
    </div>
    <div class="col-start-1 row-start-1 flex flex-col gap-4 w-full h-full z-10 relative text-brown pointer-events-none">
        <h1 class="text-[20vh] leading-46 font-semibold text-purple font-bebas">HACK CARD</h1>
        <p class="-mt-6 text-3xl max-w-lg">A printed circuit board design competition for <span class="underline text-blue-700 font-medium">all skill levels</span></p>
        <form class="form border hover:outline-1 transition-all  border-brown rounded-xs bg-white w-fit pointer-events-auto shadow-xs">
            <div class="h-14 min-w-60 lg:min-w-120 rounded-sm flex p-1.5">
                <input name="email" type="email" placeholder="johncena@hackclub.com" class="w-full px-4 focus:outline-none">
                <button class="rsvp ml-auto bg-green rounded-xs border border-brown  hover:bg-red hover:text-white transition-all cursor-pointer flex items-start gap-3 p-1 group">
                    <span class="font-semibold text-3xl font-bebas pt-1">RSVP</span>
                    <svg width="auto" height="10px" viewBox="0 0 37 37" class="group-hover:bg-red" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M3 33.8333L33.8333 3M33.8333 33.8333V3H3" stroke="#1E1E1E" stroke-width="6" stroke-linecap="round" stroke-linejoin="round"/>
                    </svg>

                </button>
            </div>
        </form>
        <div class="mt-auto w-full flex justify-between items-end">
            <h3 class="text-3xl xl:text-6xl max-w-2xl font-semibold">For teens 13-18. <br /> Begins September 10th.</h3>
            <div class="w-100 h-60 border border-brown rounded-xs shadow-xs ">
            </div>
    </div>
        </div>

    <div class="absolute top-2 text-sm lg:text-base xl:top-4 left-0 px-8 xl:px-16 w-full h-fit flex font-mono text-brown font-light gap-28">
        <span>A HACKCLUB EVENT</span>
        <span class="ml-auto">00:00:00<span class="text-gray"> /24H</span></span>
        <span>BY SOPHIA DUAN</span>
    </div>

</section>
<Footer />
