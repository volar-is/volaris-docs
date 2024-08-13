<script>
    import "$lib/global.css";
    import { fade } from "svelte/transition";
  </script>
  
  <svelte:head>
    <title>Checksums</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </svelte:head>
  
  <div
    class="min-h-screen flex flex-col bg-gray-900 text-white px-4 py-8"
    transition:fade={{ duration: 250 }}
  >
    <div class="max-w-4xl mx-auto">
      <h1 class="text-4xl sm:text-5xl font-bold mb-8 text-center text-pink-500">
        Checksums
      </h1>
  
      <section class="mb-12">
        <p class="text-lg mb-6">
          In Volaris, hashing mode uses <span class="font-semibold text-pink-400">BLAKE3</span> for verification due to its speed, security, and regular updates, making it ideal for this use case.
        </p>
        <p class="text-lg mb-6">
          Checksums in Volaris are not used for anything security-related; they are provided for your peace of mind.
        </p>
        <p class="text-lg mb-6">
          The encrypted file is hashed (after encryption and before/during decryption) to ensure that it wasn't tampered with between these stages. If the hash doesn't match, it indicates a serious issue.
        </p>
        <p class="text-lg mb-6">
          Since <span class="font-semibold text-pink-400">v8.5.0</span>, checksums are calculated after the main process. This approach helps keep our encryption/decryption functions cleaner and more focused, maintaining the core functionality effectively.
        </p>
      </section>
  
      <section class="mb-12">
        <h2 class="text-3xl font-semibold mb-4 text-pink-400">Standalone Hashing Mode</h2>
        <p class="text-lg mb-6">
          You can use standalone hashing mode by running <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">volaris-cli hash test.enc</code>. This can be done on any file—encrypted or not.
        </p>
        <p class="text-lg mb-6">
          You can even hash multiple files at once with a command like <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">volaris-cli hash test1.enc test2.enc</code>.
        </p>
      </section>
  
      <section class="mb-12">
        <h2 class="text-3xl font-semibold mb-4 text-pink-400">Performance</h2>
        <p class="text-lg mb-6">
          Performance tests were conducted on a system with a Ryzen 5 3600x and 16GB of 3200MHz RAM, running Fedora Linux. The test file was 3.5GiB and stored on a Crucial MX500 SSD.
        </p>
        <p class="text-lg mb-6">
          Version 6 removed JSON entirely and dropped base64 encoding, significantly improving performance.
        </p>
        <p class="text-lg mb-6">
          These tests were conducted using <span class="font-semibold text-pink-400">AES-256-GCM</span>.
        </p>
        <p class="bg-gray-800 p-4 rounded-lg text-pink-400 mb-6 text-center">
          Time was measured using <code>/usr/bin/time -f "%e"</code>.
        </p>
      </section>
  
      <section class="mb-12">
        <h2 class="text-3xl font-semibold mb-4 text-pink-400">Times</h2>
        <div class="overflow-hidden rounded-lg border border-gray-700">
          <table class="min-w-full text-lg">
            <thead class="bg-gray-800 text-pink-400">
              <tr>
                <th class="px-6 py-3 text-left">Option</th>
                <th class="px-6 py-3 text-left">Seconds</th>
              </tr>
            </thead>
            <tbody class="divide-y divide-gray-600">
              <tr class="bg-gray-700 odd:bg-gray-800 hover:bg-gray-600 transition-colors duration-200">
                <td class="px-6 py-4">-eHyk</td>
                <td class="px-6 py-4">5.61s</td>
              </tr>
              <tr class="bg-gray-800 odd:bg-gray-700 hover:bg-gray-600 transition-colors duration-200">
                <td class="px-6 py-4">-dHyk</td>
                <td class="px-6 py-4">5.35s</td>
              </tr>
            </tbody>
          </table>
        </div>
      </section>
    </div>
  
    <div class="flex justify-between items-center mt-12">
      <a
        href="/docs/choosing-key"
        class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
      >
        Previous
      </a>
      <a
        href="/docs/environment-variables"
        class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
      >
        Next
      </a>
    </div>
  </div>
  