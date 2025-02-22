<script>
  let { children } = $props();
  import "../app.css";
  import CtAs from "../components/CTAs.svelte";
  import Footer from "../components/Footer.svelte";
  import { openModal } from "../store/store";

  const reroute = (href) => {
    openModal.set(false);
    window.location.href = href;
  };
</script>

{#if $openModal}
  <div
    class="fixed top-0 left-0 w-screen h-screen border-b bg-white z-50 flex flex-col gap-8 p-5 px-8 md:hidden"
  >
    <div class="flex items-center justify-between gap-4 border-b pb-2">
      <h1 class="font-semibold">
        Max <span class="text-indigo-400">Fit</span>
      </h1>
      <button
        onclick={() => openModal.set(false)}
        class="outline-none border-none"
        aria-label="Close menu"
      >
        <i class="fa-solid fa-xmark text-2xl"></i>
      </button>
    </div>
    <div class="flex flex-col gap-4 flex-1">
      <button
        onclick={() => reroute("#products")}
        class="border-none outline-none p-2 group duration-200 cursor-pointer text-left"
      >
        <p class="duration-200 group-hover:pl-2 poppins text-3xl font-semibold">
          Product <i class="fa-solid fa-chevron-right text-xl pl-4"></i>
        </p>
      </button>
      <button
        onclick={() => reroute("#reviews")}
        class="border-none outline-none p-2 group duration-200 cursor-pointer text-left"
      >
        <p class="duration-200 group-hover:pl-2 poppins text-3xl font-semibold">
          Reviews <i class="fa-solid fa-chevron-right text-xl pl-4"></i>
        </p></button
      >
      <button
        onclick={() => reroute("#faqs")}
        class="border-none outline-none p-2 group duration-200 cursor-pointer text-left"
      >
        <p class="duration-200 group-hover:pl-2 poppins text-3xl font-semibold">
          FAQs <i class="fa-solid fa-chevron-right text-xl pl-4"></i>
        </p>
      </button>
    </div>
    <div class="flex flex-col items-center justify-center">
      <CtAs />
    </div>
  </div>
{/if}

{@render children()}
<Footer />
<!-- <svelte:window bind:scrollY={y} bind:outerHeight /> -->
