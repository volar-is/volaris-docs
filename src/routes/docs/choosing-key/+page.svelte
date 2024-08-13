<script>
    import "$lib/global.css";
    import { fade } from "svelte/transition";
  </script>
  
  <svelte:head>
    <title>Choosing a Key</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </svelte:head>
  
  <div
    class="min-h-screen flex flex-col text-white px-4 py-8"
    transition:fade={{ duration: 250 }}
  >
    <div class="max-w-4xl mx-auto">
      <h1 class="text-4xl sm:text-5xl font-bold mb-8 text-center text-pink-500">
        Choosing a Key
      </h1>
  
      <section class="mb-12">
        <p class="text-lg mb-6">
          When securing your data, it's crucial to use a strong password, especially if you’re planning to enter it manually.
        </p>
        <p class="text-lg mb-6">
          For an even higher level of security, you can generate a keyfile using <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">dd</code>:
        </p>
        <p class="bg-gray-800 p-4 rounded-lg text-pink-400 mb-6 text-center">
          <code>dd if=/dev/urandom of=keyfile bs=1 count=4096</code> <br/>
          (Generates a 4KB random keyfile)
        </p>
        <p class="text-lg mb-6">
          Be aware: If you lose your key or keyfile, the encrypted data is unrecoverable. This is not unique to Volaris; it's the nature of encryption itself.
        </p>
      </section>
  
      <section class="mb-12">
        <h2 class="text-3xl font-semibold mb-4 text-pink-400">Options for Providing a Key</h2>
        <p class="text-lg mb-6">
          Volaris allows you to provide keys in several ways:
        </p>
        <ul class="list-disc list-inside space-y-4">
          <li>
            <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">-k</code> to specify the path to a keyfile.
          </li>
          <li>
            <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">--auto</code> to let Volaris auto-generate a key.
          </li>
          <li>
            Set the <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">VOLARIS_KEY</code> environment variable.
          </li>
          <li>
            Provide a user-generated password (by running Volaris without any of the above).
          </li>
        </ul>
      </section>
    </div>
  
    <div class="flex justify-between items-center mt-12">
      <a
        href="/docs/installing-building"
        class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
      >
        Previous
      </a>
      <a
        href="/docs/checksums"
        class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
      >
        Next
      </a>
    </div>
  </div>
  