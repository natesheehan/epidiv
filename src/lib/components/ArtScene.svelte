<script>
  import { onMount, onDestroy } from "svelte";

  const TEXT = "We are an international reading group who meet twice a month to discuss texts in the philosophy of science, feminist epistemology, and critical data studies. To join us, hit the contact button in the footer; or if you’re interested in our reading list, check out the schedule.";

  // ⏱️ Timing (ms)
  const TYPE_SPEED = 68;      // lower = faster typing
  const HOLD_TIME  = 40000;   // how long the full sentence stays (40s)
  const ERASE_TIME = 700;     // fade-out duration before restart

  let out = "";               // currently displayed text
  let idx = 0;                // position in TEXT
  let typing = true;          // used to toggle cursor blink speed
  let fadeOut = false;        // adds a CSS class to fade the whole block
  let t1, t2, t3;             // timers

  function typeNext() {
    if (idx < TEXT.length) {
      out += TEXT[idx++];
      typing = true;
      t1 = setTimeout(typeNext, TYPE_SPEED);
    } else {
      typing = false;
      // Hold the full sentence, then fade/clear and restart
      t2 = setTimeout(() => {
        fadeOut = true;
        t3 = setTimeout(() => {
          // reset
          out = "";
          idx = 0;
          fadeOut = false;
          typeNext();
        }, ERASE_TIME);
      }, HOLD_TIME);
    }
  }

  onMount(() => { typeNext(); });
  onDestroy(() => {
    clearTimeout(t1); clearTimeout(t2); clearTimeout(t3);
  });
</script>

<svelte:head>
  <!-- Big, elegant font -->
  <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;600;700&display=swap" rel="stylesheet">
</svelte:head>

<section class="hero">
  <div class="wrapper {fadeOut ? 'fade' : ''}">
    <p class="line" aria-live="polite" aria-atomic="true">
      {out}<span class="cursor {typing ? 'blink-fast' : 'blink-slow'}"></span>
    </p>
  </div>
</section>

<style>
  .hero {
    background: #fff;
    color: #0b0b0b;
    min-height: calc(100vh - 0px);
    display: grid;
    place-items: center;
    margin-top: -5%;
    padding: 5vmin 6vmin;
    box-sizing: border-box;
    font-family: 'Space Grotesk', system-ui, -apple-system, Segoe UI, Roboto, sans-serif;
  }

  .wrapper {
    max-width: 1200px;
    width: 100%;
    transition: opacity 700ms ease, transform 700ms ease;
  }
  .wrapper.fade {
    opacity: 0;
    transform: translateY(6px);
  }

  .line {
    margin: 0 auto;
    font-weight: 600;
    line-height: 1.25;
    letter-spacing: 0.1em;
    text-wrap: balance;
    text-align: center;
    /* Responsive sizes */
    font-size: clamp(2.35rem, 4vw + 0.5rem, 3rem);
  }

  /* Cursor */
  .cursor {
    display: inline-block;
    width: 0.6ch;
    height: 1em;
    transform: translateY(0.1em);
    border-right: 0.12em solid currentColor;
  }

  @keyframes blinkFast { 0%, 49% { opacity: 1 } 50%, 100% { opacity: 0 } }
  @keyframes blinkSlow { 0%, 59% { opacity: 1 } 60%, 100% { opacity: 0 } }

  .blink-fast { animation: blinkFast 700ms steps(1) infinite; }
  .blink-slow { animation: blinkSlow 1200ms steps(1) infinite; }

  /* Respect reduced motion */
  @media (prefers-reduced-motion: reduce) {
    .cursor, .blink-fast, .blink-slow { animation: none; }
    .wrapper { transition: none; }
  }
</style>
