 <script lang="ts">
    import { Canvas } from '@threlte/core'
    import Scene from '$lib/components/Scene.svelte'
    import Navbar from '$lib/components/Navbar.svelte'
    import Footer from '$lib/components/Footer.svelte'
    import FAQ from '$lib/components/FAQ.svelte'

    import { onMount, onDestroy } from 'svelte';
    import { gsap } from 'gsap'
    import { ScrollTrigger } from 'gsap/ScrollTrigger'

    gsap.registerPlugin(ScrollTrigger)
    // let dateTime = new Date()

    let tween: gsap.core.Tween

    const faqInfo = [
      {
        id: 1,
        question: "Lorem blah blah blahahsdfjlksdlkjf?",
        answer: "Nah bro ainfdklmaldskmfaldsfmsaldf how are u the quick brown fox jumps over the lazy the dogs. How are you doing, wow."
      },
      {
        id: 2,
        question: "Lorem blah blah blahahsdfjlksdlkjf?",
        answer: "Nah bro ainfdklmaldskmfaldsfmsaldf how are u the quick brown fox jumps over the lazy the dogs. How are you doing, wow."
      },
      {
        id: 3,
        question: "Lorem blah blah blahahsdfjlksdlkjf?",
        answer: "Nah bro ainfdklmaldskmfaldsfmsaldf how are u the quick brown fox jumps over the lazy the dogs. How are you doing, wow."
      },
      {
        id: 4,
        question: "Lorem blah blah blahahsdfjlksdlkjf?",
        answer: "Nah bro ainfdklmaldskmfaldsfmsaldf how are u the quick brown fox jumps over the lazy the dogs. How are you doing, wow."
      },
    ];

    const faqGeneral = [
      {
        id: 1,
        question: "Lorem blah blah blahahsdfjlksdlkjf?",
        answer: "Nah bro ainfdklmaldskmfaldsfmsaldf how are u the quick brown fox jumps over the lazy the dogs. How are you doing, wow."
      },
      {
        id: 2,
        question: "Lorem blah blah blahahsdfjlksdlkjf?",
        answer: "Nah bro ainfdklmaldskmfaldsfmsaldf how are u the quick brown fox jumps over the lazy the dogs. How are you doing, wow."
      },
      {
        id: 3,
        question: "Lorem blah blah blahahsdfjlksdlkjf?",
        answer: "Nah bro ainfdklmaldskmfaldsfmsaldf how are u the quick brown fox jumps over the lazy the dogs. How are you doing, wow."
      },
      {
        id: 4,
        question: "Lorem blah blah blahahsdfjlksdlkjf?",
        answer: "Nah bro ainfdklmaldskmfaldsfmsaldf how are u the quick brown fox jumps over the lazy the dogs. How are you doing, wow."
      },
    ];



    onMount(() => {
        tween = gsap.from('.about', {
          yPercent: 20,
          ease: 'none',
          scrollTrigger: {
            trigger: ".trigger",
            start: 'top center',
            end: '+=500',
            scrub: true,
            // markers: true
          }
        })


    });
    onDestroy(() => {
      tween?.scrollTrigger?.kill();
      tween?.kill();
    });

</script>


<div class="fixed inset-0 bg-[url('../lib/assets/noise.gif')] opacity-8 pointer-events-none">
</div>
<section id="hero" class="noise w-screen min-h-screen p-6 bg-beige xl:p-14 grid grid-cols-1 grid-rows-1 bg-local">

    <a href="/custom" target="" class="z-100 mix-blend-multiply fixed top-1/2 right-0 -translate-y-1/2 w-12 h-40 hover:w-14 transition-all ease-in-out duration-300 bg-red text-red">
        <!-- <p class="-rotate-90 whitespace-nowrap translate-y-20 font-semibold text-white">View More</p> -->.
    </a>
    <div class="col-start-1 row-start-1 grid grid-cols-1 grid-rows-1 h-180 w-180 xl:h-220 xl:w-220 ml-auto pt-20 pr-20 place-items-center mt-30 xl:mt-0">
        <div class="col-start-1 row-start-1 z-0 relative h-full w-full">
            <Canvas>
                <Scene />
            </Canvas>
        </div>
        <div class="col-start-1 row-start-1 flex items-center justify-center w-fit h-fit font-lato font-bold">
            <Navbar />
        </div>
    </div>
    <div class="col-start-1 row-start-1 flex flex-col gap-4 w-full h-full z-10 relative text-brown pointer-events-none">
        <div class="flex items-start">
            <h1 class="sm:text-[20vh] xl:text-[13vw] leading-54 font-bebas font-semibold">HACK CARD</h1>
            <span class="text-4xl rotate-180 font-bebas mt-4">&copy;</span>
        </div>

        <h3 class="-mt-10 text-3xl max-w-lg text-dark-gray">A printed circuit board design competition for <span class="underline text-blue-700 font-medium">all skill levels</span></h3>
        <form class="form border hover:outline-1 transition-all  border-brown rounded-xs bg-white w-fit pointer-events-auto shadow-xs mt-4">
            <div class="h-14 min-w-60 lg:min-w-110 rounded-sm flex p-1.5">
                <input name="email" type="email" placeholder="johncena@hackclub.com" class="w-full px-4 focus:outline-none">
                <button class="rsvp ml-auto bg-green rounded-xs border border-brown  hover:bg-red hover:text-white transition-all cursor-pointer flex items-start gap-3 p-1 group">
                    <span class="font-semibold text-3xl font-bebas pt-1">RSVP</span>
                    <svg width="auto" height="10px" viewBox="0 0 37 37" class="group-hover:bg-red" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M3 33.8333L33.8333 3M33.8333 33.8333V3H3" stroke="#1E1E1E" stroke-width="6" stroke-linecap="round" stroke-linejoin="round"/>
                    </svg>
                </button>
            </div>
        </form>
        <div class="trigger mt-auto space-y-6">
            <h4 class="text-xl font-mono my-1">CATEGORIES:</h4>
            <ul class="font-mono text-xl leading-tight">
                <li>1) OVERALL PICK</li>
                <li>2) BEST BEGINNER PCB</li>
                <li>3) MOST ARTISTIC</li>
                <li>4) MOST NON-BUSINESS CARD LIKE</li>
                <li>5) MOST TECHNICAL</li>
            </ul>
            <h3 class="text-3xl xl:text-5xl text-brown max-w-2xl font-semibold">For teens 13-18. <br /> Begins September 10th.</h3>
        </div>
    </div>

    <div class="fixed top-2 text-sm lg:text-base xl:top-4 left-0 px-8 xl:px-16 w-full h-fit flex font-mono text-brown font-light gap-28 mix-blend-multiply">
        <span>A HACKCLUB EVENT</span>
        <span class="ml-auto">00:00:00<span class="text-gray"> /24H</span></span>
        <span>BY SOPHIA DUAN</span>
    </div>
    <div class="fixed bottom-2 text-sm lg:text-base xl:bottom-4 left-0 px-8 xl:px-16 w-full h-fit font-mono text-brown font-light ml-auto gap-14 flex justify-end mix-blend-multiply">
        <span>X 000 | Y 000</span>
        <span>&copy; 2026</span>
    </div>

</section>
<section class="bg-beige h-200 w-screen"></section>
<section class="about bg-gray h-screen w-screen opacity-50">

</section>
<section id="faq" class="bg-beige min-h-200 w-screen p-6 xl:p-14 flex flex-col">
    <h2 class="font-bebas text-9xl text-brown my-4">FAQ</h2>

    <FAQ title="GENERAL QUESTIONS" items={faqInfo} />

    <div class="pt-14"></div>

    <FAQ title="GENERAL QUESTIONS" items={faqGeneral} />

    <div class="font-bebas text-2xl text-darl-gray mt-auto">
        <span>Still have questions? <br />email me at <span class="bg-green text-red px-2 rounded-xs">sophia [@] hackclub.com</span></span>
    </div>
</section>
<section class="bg-brown h-200 w-screen p-6 xl:px-14 py-14 xl:pt-24 flex text-gray gap-10 xl:gap-60">
    <div class="w-full xl:w-1/3 space-y-4 h-full flex flex-col">
        <h3 class="font-bebas text-9xl">WHO'S BEHIND THIS?</h3>
        <p>hey i’m sophia! i’m an 18-year-old from canada who recently moved to vermont to work at hack club, a 501c(3) non profit. if you join i’m sure we’ll chat!
        </p>
        <div class="w-full h-80 bg-blue rounded-xs mt-auto"></div>
    </div>
    <div class="grow space-y-4">
        <div class="w-full h-80 bg-blue rounded-xs pt-6"></div>
        <p class="text-right max-w-2xl ml-auto mt-4">hack club is a non-profit working to empower high school students to learn coding and engineering by building real-world technical projects. we are built by teenagers, for teenagers.</p>
    </div>
    <!-- <div class="w-full h-100 mt-auto bg-beige rounded-xs"></div> -->
</section>
<Footer />
