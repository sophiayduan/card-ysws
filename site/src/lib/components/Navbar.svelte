<script>
    let { dark = "bg-brown text-beige" } = $props()
</script>
<nav class="col-start-1 row-start-1 z-10">
    <ul class="flex gap-2 uppercase text-lg font-semibold tracking-wider">
      <li class="px-2 py-0.5 rounded-[1px] w-fit {dark}">About</li>
      <li class="px-2 py-0.5 rounded-[1px] w-fit {dark}">Rules</li>
      <li class="px-2 py-0.5 rounded-[1px] w-fit {dark}">Categories</li>
      <li class="px-2 py-0.5 rounded-[1px] w-fit {dark}">Gallery</li>
      <li class="px-2 py-0.5 rounded-[1px] w-fit {dark}">FAQ</li>
    </ul>
</nav>
