<svelte:head>
  <!-- Google Font -->
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600&display=swap" rel="stylesheet">
</svelte:head>

<header class="w-full bg-white border-b font-space">
  <nav class="max-w-7xl mx-auto px-4">
    <ul class="flex flex-col md:flex-row justify-between items-center text-lg md:text-xl font-medium tracking-wide">
      <li class="py-4 md:py-6 flex-1 text-center">
        <a href="/" class="font-bold text-xxl hover:text-blue-600 transition">EpiDiv</a>
      </li>
      <li class="py-4 md:py-6 flex-1 text-center">
        <a href="#about" class="hover:text-blue-600 transition">About</a>
      </li>
      <li class="py-4 md:py-6 flex-1 text-center">
        <a href="/schedule" class="hover:text-blue-600 transition">Schedule</a>
      </li>
      <li class="py-4 md:py-6 flex-1 text-center">
        <a href="#outputs" class="hover:text-blue-600 transition">Outputs</a>
      </li>
    </ul>
  </nav>
</header>

<style>
  .font-space { 
    font-family: 'Space Grotesk', sans-serif; 
  }
</style>