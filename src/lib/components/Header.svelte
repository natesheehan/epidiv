<script>
  let open = false;
  const close = () => (open = false);
</script>

<svelte:head>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600&display=swap" rel="stylesheet">
</svelte:head>

<header class="sticky top-0 z-50 w-full bg-white/95 backdrop-blur border-b font-space">
  <nav class="relative px-4">
    <!-- Desktop: 4 items, equal columns, full width -->
    <ul class="hidden md:grid grid-cols-4 w-full text-base lg:text-lg font-medium tracking-wide">
      <li class="text-center py-4">
        <a href="/" class="hover:text-gray-600 transition font-semibold">EpiDiv</a>
      </li>
      <li class="text-center py-4">
        <a href="/info" class="hover:text-gray-600 transition">Info</a>
      </li>
      <li class="text-center py-4">
        <a href="/schedule" class="hover:text-gray-600 transition">Schedule</a>
      </li>
      <li class="text-center py-4">
        <a href="/outputs" class="hover:text-gray-600 transition">Outputs</a>
      </li>
    </ul>

    <!-- Mobile top bar -->
    <div class="md:hidden flex items-center justify-between h-14">
      <a href="/" class="text-lg font-semibold">EpiDiv</a>

      <button
        class="relative w-10 h-10 grid place-items-center rounded-lg border border-gray-200 hover:bg-gray-50 transition focus:outline-none focus-visible:ring-2 focus-visible:ring-black/40"
        aria-label="Toggle menu"
        aria-expanded={open}
        on:click={() => (open = !open)}
      >
        <span class="sr-only">Menu</span>
        <div class="burger" class:open={open}>
          <span></span><span></span><span></span>
        </div>
      </button>
    </div>

    <!-- Mobile menu: slide down OVER content with shadow -->
    <div
      class="md:hidden absolute left-0 right-0 top-full origin-top transition duration-300"
      style={`transform: scaleY(${open ? 1 : 0}); opacity:${open ? 1 : 0};`}
    >
      <div class="bg-white shadow-xl rounded-b-2xl overflow-hidden border-x border-b border-gray-200">
        <ul class="flex flex-col divide-y divide-gray-200 text-base font-medium">
          <li><a href="/" on:click={close} class="block px-4 py-3 hover:bg-gray-50 transition">EpiDiv</a></li>
          <li><a href="/info" on:click={close} class="block px-4 py-3 hover:bg-gray-50 transition">Info</a></li>
          <li><a href="/schedule" on:click={close} class="block px-4 py-3 hover:bg-gray-50 transition">Schedule</a></li>
          <li><a href="/outputs" on:click={close} class="block px-4 py-3 hover:bg-gray-50 transition">Outputs</a></li>
        </ul>
      </div>
    </div>
  </nav>
</header>

<style>
  .font-space { font-family: 'Space Grotesk', system-ui, -apple-system, Segoe UI, Roboto, sans-serif; }

  /* Burger animation */
  .burger { position: relative; width: 20px; height: 14px; }
  .burger span {
    position: absolute; left: 0; width: 100%; height: 2px; background: #111; border-radius: 1px;
    transform-origin: center; transition: transform 200ms ease, opacity 200ms ease, top 200ms ease, bottom 200ms ease;
  }
  .burger span:nth-child(1) { top: 0; }
  .burger span:nth-child(2) { top: 6px; }
  .burger span:nth-child(3) { bottom: 0; }

  .burger.open span:nth-child(1) { top: 6px; transform: rotate(45deg); }
  .burger.open span:nth-child(2) { opacity: 0; transform: translateX(-4px); }
  .burger.open span:nth-child(3) { bottom: auto; top: 6px; transform: rotate(-45deg); }
</style>
