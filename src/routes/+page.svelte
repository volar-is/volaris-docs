<script>
    import '$lib/global.css';
    import { fade } from 'svelte/transition';
  </script>
  
  <svelte:head>
    <title>Volaris Documentation</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </svelte:head>
  
  <div class="flex items-center justify-center min-h-screen px-4 py-12 bg-black bg-opacity-80">
    <div class="text-center max-w-3xl w-full">
      <h1 class="text-4xl sm:text-5xl font-extrabold text-white mb-8" transition:fade={{ duration: 250 }}>Welcome to Volaris Documentation</h1>
      <p class="text-base sm:text-lg text-white mb-8 sm:mb-12" transition:fade={{ duration: 250 }}>
        Discover how to use Volaris, your comprehensive encryption solution. Our documentation provides detailed guides, FAQs, and resources to help you get started and make the most of our powerful tools.
      </p>
      <div class="flex flex-wrap justify-center gap-4 mb-12">
        <a href="/getting-started" class="bg-white text-black font-semibold py-3 px-6 rounded-lg shadow-md hover:bg-gray-200 transition duration-300" transition:fade={{ duration: 250 }}>
          Getting Started
        </a>
        <a href="/guides" class="bg-pink-600 text-white font-semibold py-3 px-6 rounded-lg shadow-md hover:bg-pink-500 transition duration-300" transition:fade={{ duration: 250 }}>
          Guides
        </a>
        <a href="/faq" class="bg-gray-700 text-white font-semibold py-3 px-6 rounded-lg shadow-md hover:bg-gray-600 transition duration-300" transition:fade={{ duration: 250 }}>
          FAQ
        </a>
      </div>
      <p class="text-base sm:text-lg text-white mb-6" transition:fade={{ duration: 250 }}>
        For more help, visit our <a href="/support" class="text-pink-400 hover:underline">Support Page</a> or see our <a href="/changelog" class="text-pink-400 hover:underline">Changelog</a> for the latest updates.
      </p>
    </div>
  </div>
  