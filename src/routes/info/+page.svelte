<script>
  import Header from "$lib/components/Header.svelte";
  import Footer from "$lib/components/Footer.svelte";

   const recipients = [
    'ns651@exeter.ac.uk',
    'rose.trappes@uib.no'
  ];
  const subject = encodeURIComponent('Epistemic Diversity reading group');

</script>

<svelte:head>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600;700&display=swap" rel="stylesheet">
</svelte:head>

<Header />

<section class="min-h-screen bg-white text-neutral-900 font-[Space_Grotesk]">
  <!-- Hero -->
  <div class="max-w-5xl mx-auto px-4 pt-14 md:pt-20">
    <h1 class="text-3xl md:text-5xl font-semibold leading-tight tracking-tight text-balance">
      For Forks’ Sake: why epistemic diversity matters.
    </h1>
    <p class="mt-4 md:mt-6 text-base md:text-lg text-neutral-600 max-w-3xl">
      An introduction to the EpiDiv reading group—where we explore how diverse perspectives shape and enrich scientific knowledge.
    </p>
    <div class="mt-6 flex flex-wrap gap-3">
      <a href="/schedule"
         class="inline-flex items-center rounded-full border border-neutral-900 px-4 py-2 text-sm font-medium hover:bg-neutral-900 hover:text-white transition">
        View schedule
      </a>
      <a href="/outputs"
         class="inline-flex items-center rounded-full border border-neutral-200 px-4 py-2 text-sm font-medium hover:bg-neutral-100 transition">
        See outputs
      </a>
    </div>
  </div>

  <!-- Body content -->
  <div class="max-w-5xl mx-auto px-4 mt-10 md:mt-14 pb-20">
    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 lg:gap-12">
      <!-- Main narrative -->
      <article class="lg:col-span-8 text-pretty">
        <p class="text-base md:text-lg leading-relaxed">
          Imagine a kitchen. Maybe the one you have at home, or perhaps the one you saw on <em>MasterChef</em>. You open the drawers, and they are filled to the brim with a single utensil: forks. Gleaming, identical forks. Every drawer, every cabinet, forks upon forks.
        </p>
        <p class="mt-4 text-base md:text-lg leading-relaxed">
          Your friend comes over, eager to bake a complex, multi-layered cake, requiring delicate folding, precise mixing, intricate decorations. But all you have is forks. Sure, forks can be used for some things, but they lack the versatility for the task at hand. Frustration mounts and together you cry: <strong>“For Forks’ Sake!”</strong>
        </p>
        <p class="mt-4 text-base md:text-lg leading-relaxed">
          Now, if you will, imagine a kitchen filled with a variety of tools: whisks, spatulas, knives of all sizes, measuring cups, and even a pestle and mortar tucked in the corner. Each tool, with its unique design and function, is ready to be utilised. Your knowledge, combined with this diverse array of utensils, turns the kitchen into a haven of possibility. Baking that intricate layer cake? Easy.
        </p>

        <!-- Pull quote -->
        <figure class="mt-8 md:mt-10 border-l-2 border-neutral-900/60 pl-4 md:pl-6">
          <blockquote class="text-lg md:text-xl leading-relaxed font-medium">
            “Now, you take that layer cake and cut into history as if it were a layer cake and begin to unpack the layers of meanings. Unpack the layers of meanings of all of the pleasures and all of the problems that these layers of meanings produce.”
          </blockquote>
          <figcaption class="mt-3 text-sm text-neutral-600">
            — Donna Haraway, <em>Paper Tiger Television Series #126</em> (1987)
          </figcaption>
        </figure>

        <p class="mt-8 text-base md:text-lg leading-relaxed">
          This kookie pretext brings us nicely to introduce our <strong>Epistemic Diversity (EpiDiv)</strong> reading group. Much like the diverse kitchen and the layered cake, our group aims to unpack the multiple layers of meaning within scientific and philosophical discourses—delving into the intersections of gender, race, and knowledge to explore how diverse perspectives shape and enrich scientific knowledge.
        </p>

        <p class="mt-8 text-base md:text-lg leading-relaxed">
          The reading group is currently curated & cordinated by <a class="text-gray-600 font-bold" href="https://rosetrappes.wordpress.com/">Rose Trappes</a> and <a class="text-gray-600 font-bold" href="https://nsheehan.vercel.app/">Nathanael Sheehan</a>. The group meets every two weeks and reads texts primarily in English. Discussions are typically facilitated using the <a class="text-gray-600 font-bold" href="https://www.sessionlab.com/methods/finger-rules">finger rule.</a>
        </p>
      </article>

      <!-- Side card: meeting times -->
      <aside class="lg:col-span-4">
        <div class="rounded-2xl border border-neutral-200 p-5 md:p-6 sticky top-6">
          <h2 class="text-lg font-semibold">Meeting times</h2>
          <p class="mt-1 text-sm text-neutral-600">Starting again in <strong>September</strong>. Fortnightly on Fridays (90 minutes).</p>
          <ul class="mt-4 space-y-2 text-sm">
            <li class="flex items-center justify-between rounded-lg border border-neutral-100 px-3 py-2">
              <span class="text-neutral-600">BST/GMT</span>
              <span class="font-medium">14:00–15:30</span>
            </li>
            <li class="flex items-center justify-between rounded-lg border border-neutral-100 px-3 py-2">
              <span class="text-neutral-600">CEST/CET</span>
              <span class="font-medium">15:00–16:30</span>
            </li>
            <li class="flex items-center justify-between rounded-lg border border-neutral-100 px-3 py-2">
              <span class="text-neutral-600">BRT</span>
              <span class="font-medium">10:00–11:30</span>
            </li>
            <li class="flex items-center justify-between rounded-lg border border-neutral-100 px-3 py-2">
              <span class="text-neutral-600">ET</span>
              <span class="font-medium">09:00–10:30</span>
            </li>
          </ul>
          <div class="mt-5 flex flex-wrap gap-2">
            <a href="/schedule"
               class="inline-flex items-center rounded-full border border-neutral-900 px-3 py-1.5 text-sm font-medium hover:bg-neutral-900 hover:text-white transition">
              See upcoming sessions
            </a>
            <a class="inline-flex items-center rounded-full border border-neutral-200 px-3 py-1.5 text-sm font-medium hover:bg-neutral-100 transition" href={`mailto:${recipients.join(',')}?subject=${subject}`}>
          Contact to join
        </a>
          </div>
        </div>
      </aside>
    </div>

    <!-- Closing CTA -->
    <div class="mt-12 md:mt-16 rounded-2xl border border-neutral-200 p-6 md:p-8 bg-neutral-50/50">
      <div class="flex flex-col md:flex-row md:items-center md:justify-between gap-4">
        <p class="text-base md:text-lg text-neutral-800">
          Fancy joining? Browse the <a href="/schedule" class="underline underline-offset-2 hover:text-gray-700">schedule</a> or <a href={`mailto:${recipients.join(',')}?subject=${subject}`} class="underline underline-offset-2 hover:text-gray-700">contact</a> us to join in.
        </p>
        <a href="/schedule"
           class="inline-flex items-center justify-center rounded-full border border-neutral-900 px-4 py-2 text-sm font-medium hover:bg-neutral-900 hover:text-white transition">
          Explore the reading list
        </a>
      </div>
    </div>
  </div>
</section>

<!-- Add an id so the footer "Contact" link can be targeted if you like -->
<div id="footer-contact"></div>

<Footer />

<style>
  /* Fallback if Tailwind isn't present */
  :global(html) { font-family: 'Space Grotesk', system-ui, -apple-system, Segoe UI, Roboto, sans-serif; }
  .text-balance { text-wrap: balance; }
  .text-pretty { text-wrap: pretty; }
</style>
