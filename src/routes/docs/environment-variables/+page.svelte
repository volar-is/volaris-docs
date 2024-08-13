<script>
    import "$lib/global.css";
    import { fade } from "svelte/transition";
  </script>
  
  <svelte:head>
    <title>Environment Variables</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </svelte:head>
  
  <div
    class="min-h-screen flex flex-col bg-gray-900 text-white px-4 py-8"
    transition:fade={{ duration: 250 }}
  >
    <div class="max-w-4xl mx-auto">
      <h1 class="text-4xl sm:text-5xl font-bold mb-8 text-center text-pink-500">
        Environment Variables
      </h1>
  
      <section class="mb-12">
        <p class="text-lg mb-6">
          Volaris can read your key from an environment variable. To do this, set the <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">VOLARIS_KEY</code> variable, and Volaris will automatically detect and use it for encryption and decryption.
        </p>
        <p class="text-lg mb-6">
          Even though Volaris uses different salts and nonces for each encryption operation, which mitigates risks associated with reusing keys, it is still not considered best practice to reuse keys across different sessions or files.
        </p>
        <p class="text-lg mb-6">
          For example, you can set the environment variable in a Unix-based system like this:
        </p>
        <p class="bg-gray-800 p-4 rounded-lg text-pink-400 mb-6 text-center">
          export VOLARIS_KEY="your_key_here"
        </p>
        <p class="text-lg mb-6"> 
          After setting the environment variable, Volaris will automatically pick up the key from <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">VOLARIS_KEY</code> when running encryption or decryption commands.
        </p>
      </section>
  
      <div class="flex justify-between items-center mt-12">
        <a
          href="/docs/checksums"
          class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
        >
          Previous
        </a>
        <a
          href="/docs/usage-examples"
          class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
        >
          Next
        </a>
      </div>
    </div>
  </div>
  