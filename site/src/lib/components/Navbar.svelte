<script>
    let { dark = "bg-brown text-beige" } = $props()
</script>
<nav class="col-start-1 row-start-1 z-10">
    <ul class="flex gap-2 font-medium">
      <li class="px-2 py-0.5 w-fit text-lg {dark} font-semibold">ABOUT</li>
      <li class="px-2 py-0.5 w-fit text-lg {dark} font-semibold">RULES</li>
      <li class="px-2 py-0.5 w-fit text-lg {dark} font-semibold">CATEGORIES</li>
      <li class="px-2 py-0.5 w-fit text-lg {dark} font-semibold">GALLERY</li>
      <li class="px-2 py-0.5 w-fit text-lg {dark} font-semibold">FAQ</li>
    </ul>
</nav>
