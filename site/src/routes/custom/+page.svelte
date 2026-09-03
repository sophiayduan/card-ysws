<script lang="ts">
    import Navbar from '$lib/components/Navbar.svelte'
</script>
<section class="h-screen w-screen bg-brown relative flex items-center justify-center p-6 px-10 xl:p-14">
    <div class="fixed top-6 left-1/2 -translate-x-1/2">
        <Navbar dark="bg-gray text-brown"/>
    </div>
    <div class="lg:max-w-[80%] xl:max-w-[60%] flex items-start justify-center gap-8 xl:gap-14">

    <div class="bg-gray rounded-sm min-w-80 h-110 rotate-4"></div>
    <div class="text-beige mt-6">
        <h2 class="text-5xl font-semibold font-bebas">[ITEM NAME]</h2>
        <h4 class="text-xl font-medium text-green italic">Some lorem ipsum ass item description or something here.</h4>
        <p>
            <br />
            Lorem Ipsum has been the industry's standard dummy text ever since 1966, when designers at Letraset and James Mosley, the librarian at St Bride Printing Library in London, took a 1914 Cicero translation and scrambled it to make dummy text for Letraset's Body Type sheets.
            <br />
            <br />
            It has survived not only many decades, but also the leap into electronic typesetting, remaining essentially unchanged.

            </p>
            <div class="mt-8 w-full flex gap-2 justify-end">
                <a href="/" class="h-full px-2 py-0.5 bg-green text-brown font-semibold">GITHUB</a>
                <a href="/" class="h-full px-2 py-0.5 bg-red text-beige font-semibold">GITHUB</a>
            </div>
    </div>
    <div class="absolute top-1/2 right-0 -translate-y-1/2 w-12 h-40 bg-red"></div>

</div>
</section>
