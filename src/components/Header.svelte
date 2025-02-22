<script>
  import { openModal } from "../store/store";
</script>

<header class="flex flex-col relative z-20">
  <div
    class="max-w-[1400px] mx-auto w-full flex items-center justify-between p-4 py-6"
  >
    <a href="/">
      <h1 class="font-semibold text-2xl">
        Max<span class="text-indigo-400 text-xl">Fit</span>
      </h1>
    </a>
    <button
      onclick={() => ($openModal = true)}
      aria-label="Open menu"
      class="md:hidden grid place-items-center"
    >
      <i class="fa-solid fa-bars"></i>
    </button>
    <nav class="hidden md:flex items-center gap-4 lg:gap-6 font-semibold">
      <a
        href="#products"
        class="duration-200 hover:text-indigo-400 cursor-pointer">Products</a
      >
      <a
        href="#reviews"
        class="duration-200 hover:text-indigo-400 cursor-pointer">Reviews</a
      >
      <a href="#faqs" class="duration-200 hover:text-indigo-400 cursor-pointer"
        >FAQs</a
      >
      <button class="spesialBtn"><p>Get Started</p></button>
    </nav>
  </div>
</header>
