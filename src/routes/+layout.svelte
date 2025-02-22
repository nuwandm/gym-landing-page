<script>
  import "../app.css";
  import CtAs from "../components/CTAs.svelte";
  import Footer from "../components/Footer.svelte";
  import Header from "../components/Header.svelte";
  import { openModal } from "../store/store";

  let whatsappNumber = "+94714557027";
  let y;
  $: outerHeight = 0;

  function reroute(href) {
    $openModal = false;
    window.location.href = href;
  }
</script>

{#if $openModal}
  <div
    class="fixed top-0 left-0 w-screen h-screen border-b bg-white z-50 flex flex-col gap-8 p-5 px-8 md:hidden"
  >
    <div class="flex items-center justify-between gap-4 border-b pb-2">
      <h1 class="font-semibold">
        Mac <span class="text-indigo-400">Fit</span>
      </h1>
      <button
        onclick={() => ($openModal = false)}
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
        </p>
      </button>
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

{#if y > outerHeight}
  <div
    class="bg-white fixed top-0 left-0 w-full flex flex-col z-20 px-4 fadeIn"
  >
    <Header />
  </div>
{/if}

<div class="fixed bottom-6 right-6 z-50">
  <a
    href={`https://wa.me/${whatsappNumber}`}
    target="_blank"
    class="flex items-center gap-3 bg-green-500 text-white px-5 py-3 rounded-full shadow-xl
           hover:bg-green-600 transition-all duration-300 ease-in-out transform hover:scale-105 animate-bounce"
    aria-label="Chat on WhatsApp"
  >
    <i class="fa-brands fa-whatsapp text-3xl"></i>
    <span class="text-lg font-semibold">Chat With Us</span>
  </a>
</div>

<slot />
<Footer />
<svelte:window bind:scrollY={y} bind:outerHeight />

<!-- header
hero
product description
user reviews
faq
conversion-
footer -->
