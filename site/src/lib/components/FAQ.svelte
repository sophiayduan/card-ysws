<script lang="ts">
    import { gsap } from 'gsap';

    type FaqItem = { id: number; question: string; answer: string };

    let { title, items }: { title: string; items: FaqItem[] } = $props();

    let openIndex = $state<number | null>(null)
    let answers: HTMLDivElement[] = $state([])
    async function toggle(index: number) {
      const isOpening = openIndex !== index;
      const el = answers[index];
      if(!el) return;

      gsap.killTweensOf(el);

      if (openIndex !== null && openIndex !== index) {
        const prevEl = answers[openIndex];
        if (prevEl) {
          gsap.to(answers[openIndex],{
            height:0,
            duration: 0.3,
            ease: 'power2.out',
          });
        }

      }
      if (isOpening) {
        openIndex = index;
        gsap.set(el, { height: 'auto' });
        const autoHeight = el.offsetHeight;
        gsap.fromTo(el, {
          height:0
        },
        { height: autoHeight,
          duration: 0.3,
          ease: 'power2.out'
        });
      } else {
        gsap.to(el, {
          height: 0,
          duration: 0.3,
          ease: 'power2.out'
        });
        openIndex = null;
      }
    }
</script>

<hr />
   <div class="flex">
       <div class="w-full py-4 text-xl font-semibold px-4">
           {title}
       </div>
       <div></div>
       <div class="w-full">
           {#each items as item, index}
           <div class="w-full py-2 xl:py-4 text-lg xl:text-xl leading-tight font-semibold px-4 border-b border-brown font-mono flex flex-col transition-all duration-300">
               <button onclick={() => toggle(index)} class="flex items-center xl:justify-between cursor-pointer">
                   <span class="text-left py-2 xl:py-4 w-fit">{item.question}</span>
                   <svg
                       width="23"
                       height="23"
                       viewBox="0 0 31 31"
                       fill="none"
                       xmlns="http://www.w3.org/2000/svg"
                       class="transition-all duration-300"
                       style:transform = {openIndex === index ? 'rotate(45deg)' : 'none'}
                   >
                       <path d="M15.5 1.5V29.5M1.5 15.5H29.5" stroke="#262A2D" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                   </svg>
               </button>
               <div bind:this={answers[index]} class="overflow-hidden h-0">
                   <span class=" text-gray leading-snug text-base transition-all py-2">{item.answer}</span>
               </div>
           </div>
           {/each}
       </div>
   </div>
