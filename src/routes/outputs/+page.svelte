<script>
  import Header from "$lib/components/Header.svelte";
  import Footer from "$lib/components/Footer.svelte";

  // 🔎 Add more outputs here as you produce them
  const outputs = [
    {
      date: "2025-06-20",
      title: "ConceptCartography",
      summary:
        "A representation of conceptual space: a topography of concepts, theories, and hypotheses and their interlinkages around epistemic diversity.",
      links: [
        { label: "Website", url: "https://conceptcartography.github.io/conceptcartography/" }
      ]
    }
  ];
</script>

<svelte:head>
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600&display=swap" rel="stylesheet">
</svelte:head>

<Header />

<section class="min-h-screen bg-white text-neutral-900 font-[Space_Grotesk]">
  <div class="max-w-6xl mx-auto px-4 pt-10 pb-16">
    <p class="text-center font-semibold">
      The EpiDiv reading group has produced several outputs over its duration.
    </p>

    <!-- Mobile: card layout -->
    <div class="mt-6 grid gap-4 md:hidden">
      {#each outputs as o}
        <article class="rounded-xl border border-neutral-200 p-4">
          <div class="flex items-baseline justify-between gap-3">
            <h3 class="font-semibold">{o.title}</h3>
            <span class="text-xs px-2 py-1 rounded-full bg-neutral-100">
              {new Date(o.date).toLocaleDateString(undefined, { year:'numeric', month:'2-digit', day:'2-digit' })}
            </span>
          </div>

          {#if o.summary}
            <p class="mt-2 text-sm leading-relaxed">{o.summary}</p>
          {/if}

          {#if o.links?.length}
            <div class="mt-3">
              <h4 class="text-sm font-medium text-neutral-600">Links</h4>
              <ul class="mt-1 space-y-1 text-sm">
                {#each o.links as l}
                  <li>
                    <a class="underline underline-offset-2 hover:text-blue-700" href={l.url} target="_blank" rel="noopener noreferrer">
                      {l.label}
                    </a>
                  </li>
                {/each}
              </ul>
            </div>
          {/if}

        
        </article>
      {/each}
    </div>

    <!-- Desktop: table layout (matches your Schedule table styling) -->
    <div class="hidden md:block mt-6 overflow-x-auto rounded-xl border border-neutral-200">
      <table class="w-full text-left text-sm">
        <thead class="bg-neutral-50 text-neutral-600">
          <tr>
            <th class="px-4 py-3 w-32">Date</th>
            <th class="px-4 py-3 w-80">Output</th>
            <th class="px-4 py-3">Summary</th>
            <th class="px-4 py-3">Links</th>
           
          </tr>
        </thead>
        <tbody>
          {#each outputs as o, i}
            <tr class={i % 2 ? 'bg-white' : 'bg-neutral-50/40'}>
              <td class="align-top px-4 py-3 whitespace-nowrap text-neutral-700">
                {new Date(o.date).toLocaleDateString(undefined, { year:'numeric', month:'2-digit', day:'2-digit' })}
              </td>
              <td class="align-top px-4 py-3 font-semibold">
                {#if o.links && o.links[0]}
                  <a class="underline underline-offset-2 hover:text-blue-700"
                     href={o.links[0].url} target="_blank" rel="noopener noreferrer">{o.title}</a>
                {:else}
                  {o.title}
                {/if}
              </td>
              <td class="align-top px-4 py-3">{o.summary}</td>
              <td class="align-top px-4 py-3">
                {#if o.links?.length}
                  <ul class="list-disc pl-5 space-y-1">
                    {#each o.links as l}
                      <li>
                        <a class="underline underline-offset-2 hover:text-blue-700"
                           href={l.url} target="_blank" rel="noopener noreferrer">{l.label}</a>
                      </li>
                    {/each}
                  </ul>
                {/if}
              </td>
    
            </tr>
          {/each}
        </tbody>
      </table>
    </div>


  </div>
</section>

<Footer />

<style>
  /* Fallback font if Tailwind isn't present */
  :global(html) { font-family: 'Space Grotesk', system-ui, -apple-system, Segoe UI, Roboto, sans-serif; }
</style>
