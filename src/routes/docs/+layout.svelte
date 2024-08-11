<script>
  import { fade } from "svelte/transition";
  let technicalDetailsOpen = false;
  let volarisCoreOpen = false;

  function toggleDropdown(dropdown) {
    if (dropdown === "technicalDetails") {
      technicalDetailsOpen = !technicalDetailsOpen;
    } else if (dropdown === "volarisCore") {
      volarisCoreOpen = !volarisCoreOpen;
    }
  }
</script>

<svelte:head>
  <title>Volaris Documentation</title>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<div class="flex flex-col md:flex-row min-h-screen bg-gray-900">
  <aside class="w-full md:w-64 bg-gray-800 text-white flex-shrink-0">
    <div class="p-4 md:p-6">
      <h2
        class="text-2xl md:text-3xl font-bold mb-6 text-pink-500 text-center md:text-left"
      >
        Volaris Docs
      </h2>
      <nav class="space-y-3">
        <a
          href="/docs/introduction"
          class="block hover:text-pink-400 transition duration-200"
          >1. Introduction</a
        >
        <a
          href="/docs/installing-building"
          class="block hover:text-pink-400 transition duration-200"
          >2. Installing and Building</a
        >
        <a
          href="/docs/choosing-key"
          class="block hover:text-pink-400 transition duration-200"
          >3. Choosing a Key</a
        >
        <a
          href="/docs/checksums"
          class="block hover:text-pink-400 transition duration-200"
          >4. Checksums</a
        >
        <a
          href="/docs/environment-variables"
          class="block hover:text-pink-400 transition duration-200"
          >5. Environment Variables</a
        >
        <a
          href="/docs/usage-examples"
          class="block hover:text-pink-400 transition duration-200"
          >6. Usage Examples</a
        >

        <div>
          <div class="w-full md:w-64 bg-gray-800 text-white flex-shrink-0">
            <a
              href="/docs/technical-details"
              class="block hover:text-pink-400 transition duration-200"
              >7. Technical Details</a
            >
            <button
              class="focus:outline-none hover:text-pink-400 transition duration-200"
              on:click={() => toggleDropdown("technicalDetails")}
            >
              <span>{technicalDetailsOpen ? "▲" : "▼"}</span>
            </button>
          </div>
          <div
            class={`mt-2 space-y-2 ${technicalDetailsOpen ? "block" : "hidden"}`}
          >
            <a
              href="/docs/technical-details/keys"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >7.1. Keys</a
            >
            <a
              href="/docs/technical-details/secure-erase"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >7.2. Secure Erase</a
            >
            <a
              href="/docs/technical-details/directory-packing"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >7.3. Directory Packing</a
            >
            <a
              href="/docs/technical-details/performance-notes"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >7.4. Performance Notes</a
            >
          </div>
        </div>

        <div>
          <div class="w-full md:w-64 bg-gray-800 text-white flex-shrink-0">
            <a
              href="/docs/volaris-core"
              class="block hover:text-pink-400 transition duration-200"
              >8. Volaris-Core</a
            >
            <button
              class="focus:outline-none hover:text-pink-400 transition duration-200"
              on:click={() => toggleDropdown("volarisCore")}
            >
              <span>{volarisCoreOpen ? "▲" : "▼"}</span>
            </button>
          </div>
          <div class={`mt-2 space-y-2 ${volarisCoreOpen ? "block" : "hidden"}`}>
            <a
              href="/docs/volaris-core/headers"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >8.1. Headers</a
            >
            <a
              href="/docs/volaris-core/password-hashing"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >8.2. Password Hashing</a
            >
            <a
              href="/docs/volaris-core/encryption"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >8.3. Encryption</a
            >
            <a
              href="/docs/volaris-core/protected-wrapper"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >8.4. Protected Wrapper</a
            >
            <a
              href="/docs/volaris-core/api-documentation"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >8.5. API Documentation</a
            >
            <a
              href="/docs/volaris-core/auditing"
              class="block py-1 pl-6 hover:bg-gray-700 rounded transition duration-200"
              >8.6. Auditing</a
            >
          </div>
        </div>

        <a
          href="/docs/volaris-tools"
          class="block hover:text-pink-400 transition duration-200"
          >9. Volaris-Tools</a
        >
        <a
          href="/docs/security-policy"
          class="block hover:text-pink-400 transition duration-200"
          >10. Security Policy</a
        >
        <a
          href="/docs/supporting-volaris"
          class="block hover:text-pink-400 transition duration-200"
          >11. Supporting Volaris</a
        >
      </nav>
    </div>
  </aside>

  <main class="flex-grow bg-gray-900 text-white p-4 md:p-8">
    <div class="content">
      <slot></slot>
    </div>
  </main>
</div>

<style>
  @media (max-width: 768px) {
    .block {
      display: block;
      text-align: left;
    }
    .hidden {
      display: none;
    }
    .flex {
      flex-direction: column;
    }
    .p-4 {
      padding: 1rem;
    }
    .w-full {
      width: 100%;
    }
    .pl-6 {
      padding-left: 1.5rem; 
    }
  }
</style>
