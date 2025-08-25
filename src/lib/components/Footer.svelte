<script>
  import { onMount } from 'svelte';

  let now = new Date();
  onMount(() => {
    const t = setInterval(() => (now = new Date()), 1000);
    return () => clearInterval(t);
  });

  const recipients = [
    'ns651@exeter.ac.uk',
    'rose.trappes@uib.no'
  ];
  const subject = encodeURIComponent('Epistemic Diversity reading group');

  function fmt(d) {
    return d.toLocaleString(undefined, {
      weekday: 'short',
      year: 'numeric',
      month: 'short',
      day: '2-digit',
      hour: '2-digit',
      minute: '2-digit',
      second: '2-digit'
    });
  }
</script>

<svelte:head>
  <!-- Footer font -->
  <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;600&display=swap" rel="stylesheet">
</svelte:head>

<footer class="w-full bg-white border-t font-plex">
  <!-- Logos row -->
  <div class="max-w-6xl mx-auto px-4 pt-8">
    <div class="flex items-center justify-center gap-8 md:gap-10 flex-wrap">
      <img
        src="./bergen.svg"
        alt="Bergen logo"
        class="w-24 h-12 md:w-28 md:h-14 object-contain fade-in-once"
        style="animation-delay: 0s"
      />
      <img
        src="./tum.svg"
        alt="TUM logo"
        class="w-24 h-12 md:w-28 md:h-14 object-contain fade-in-once"
        style="animation-delay: 0.2s"
      />
      <img
        src="./Phil_OS.png"
        alt="Phil_OS logo"
        class="w-24 h-12 md:w-28 md:h-14 object-contain fade-in-once"
        style="animation-delay: 0.4s"
      />
    </div>
  </div>

  <!-- Divider -->
  <div class="max-w-6xl mx-auto px-4">
    <hr class="mt-8 border-gray-200" />
  </div>

  <!-- Bottom row -->
  <div class="max-w-6xl mx-auto px-4 py-4">
    <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-2 text-sm md:text-base">
      <!-- Left: local time -->
      <div class="text-gray-700">
        {fmt(now)}
      </div>

      <!-- Right: Contact link -->
      <div class="text-gray-700">
        <a
          class="underline underline-offset-4 hover:text-blue-600 transition"
          href={`mailto:${recipients.join(',')}?subject=${subject}`}
        >
          Contact
        </a>
      </div>
    </div>
  </div>
</footer>

<style>
  .font-plex { font-family: "IBM Plex Mono", ui-monospace, SFMono-Regular, Menlo, monospace; }

  /* One-time fade-in animation */
  @keyframes fadeOnce {
    from { opacity: 0; transform: translateY(6px); }
    to   { opacity: 1; transform: translateY(0); }
  }
  .fade-in-once {
    opacity: 0;
    animation: fadeOnce 700ms ease-out forwards;
  }

  @media (prefers-reduced-motion: reduce) {
    .fade-in-once {
      animation: none;
      opacity: 1;
      transform: none;
    }
  }
</style>
