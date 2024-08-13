<script>
  let sidebarOpen = false;
  let technicalDetailsOpen = false;
  let volarisCryptoOpen = false;
  let aboutUsOpen = false;

  function toggleSidebar() {
    sidebarOpen = !sidebarOpen;
  }

  function toggleDropdown(dropdown) {
    if (dropdown === "technicalDetails") {
      technicalDetailsOpen = !technicalDetailsOpen;
    } else if (dropdown === "volarisCrypto") {
      volarisCryptoOpen = !volarisCryptoOpen;
    } else if (dropdown === "aboutUs") {
      aboutUsOpen = !aboutUsOpen;
    }
  }
</script>

<svelte:head>
  <title>Volaris Documentation</title>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<div class="flex flex-col md:flex-row min-h-screen bg-gray-900 text-white">
  <button
    class="md:hidden fixed top-4 left-4 z-50 p-2 bg-gray-800 text-white rounded-full shadow-lg"
    on:click={toggleSidebar}
    aria-label="Toggle Sidebar"
  >
    <span class="material-icons">menu</span>
  </button>

  <aside
    class={`fixed top-0 left-0 w-72 shadow-lg flex-shrink-0 transition-transform duration-300 border-r border-gray-700 bg-gray-800 md:static md:translate-x-0 ${sidebarOpen ? 'translate-x-0' : '-translate-x-full'}`}
  >
    <div class="p-6">
      <a href="/">
        <h2
          class="items-center py-3 px-4 rounded-lg text-4xl font-bold mb-8 text-white text-center md:text-left"
        >
          <span class="block text-pink-400">Volaris</span>Docs
        </h2>
      </a>
      <nav class="space-y-2">
        <div class="relative">
          <div
            class="flex items-center justify-between py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300 cursor-pointer"
            on:click={() => toggleDropdown("aboutUs")}
          >
            <div class="flex items-center">
              <span class="material-icons text-lg mr-3">info</span>
              <span>About Us</span>
            </div>
            <span class="material-icons text-lg">{aboutUsOpen ? "expand_less" : "expand_more"}</span>
          </div>
          <div
            class={`mt-2 space-y-2 pl-8 ${aboutUsOpen ? "block" : "hidden"}`}
          >
            <a
              href="/docs/about-us/team"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Team
            </a>
            <a
              href="/docs/about-us/careers"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Careers
            </a>
            <a
              href="/docs/about-us/contact"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Contact Us
            </a>
          </div>
        </div>

        <a
            href="/docs/introduction"
            class="flex items-center py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300"
          >
            <span class="material-icons text-lg mr-3">home</span>
            <span>Introduction</span>
          </a>

        <a
          href="/docs/installing-building"
          class="flex items-center py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300"
        >
          <span class="material-icons text-lg mr-3">build</span>
          <span>Installing and Building</span>
        </a>
        <a
          href="/docs/choosing-key"
          class="flex items-center py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300"
        >
          <span class="material-icons text-lg mr-3">vpn_key</span>
          <span>Choosing a Key</span>
        </a>
        <a
          href="/docs/checksums"
          class="flex items-center py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300"
        >
          <span class="material-icons text-lg mr-3">check_circle</span>
          <span>Checksums</span>
        </a>
        <a
          href="/docs/environment-variables"
          class="flex items-center py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300"
        >
          <span class="material-icons text-lg mr-3">settings</span>
          <span>Environment Variables</span>
        </a>
        <a
          href="/docs/usage-examples"
          class="flex items-center py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300"
        >
          <span class="material-icons text-lg mr-3">code</span>
          <span>Usage Examples</span>
        </a>

        <div class="relative">
          <div
            class="flex items-center justify-between py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300 cursor-pointer"
            on:click={() => toggleDropdown("technicalDetails")}
          >
            <div class="flex items-center">
              <span class="material-icons text-lg mr-3">description</span>
              <span>Technical Details</span>
            </div>
            <span class="material-icons text-lg">{technicalDetailsOpen ? "expand_less" : "expand_more"}</span>
          </div>
          <div
            class={`mt-2 space-y-2 pl-8 ${technicalDetailsOpen ? "block" : "hidden"}`}
          >
            <a
              href="/docs/technical-details/keys"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Keys
            </a>
            <a
              href="/docs/technical-details/secure-erase"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Secure Erase
            </a>
            <a
              href="/docs/technical-details/directory-packing"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Directory Packing
            </a>
            <a
              href="/docs/technical-details/performance-notes"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Performance Notes
            </a>
          </div>
        </div>

        <div class="relative">
          <div
            class="flex items-center justify-between py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300 cursor-pointer"
            on:click={() => toggleDropdown("volarisCrypto")}
          >
            <div class="flex items-center">
              <span class="material-icons text-lg mr-3">layers</span>
              <span>Volaris-Crypto</span>
            </div>
            <span class="material-icons text-lg">{volarisCryptoOpen ? "expand_less" : "expand_more"}</span>
          </div>
          <div
            class={`mt-2 space-y-2 pl-8 ${volarisCryptoOpen ? "block" : "hidden"}`}
          >
            <a
              href="/docs/volaris-crypto/"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              About Volaris-Crypto
            </a>
            <a
              href="/docs/volaris-crypto/headers"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Headers
            </a>
            <a
              href="/docs/volaris-crypto/password-hashing"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Password Hashing
            </a>
            <a
              href="/docs/volaris-crypto/encryption"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Encryption
            </a>
            <a
              href="/docs/volaris-crypto/protected-wrapper"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Protected Wrapper
            </a>
            <a
              href="/docs/volaris-crypto/api-documentation"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              API Documentation
            </a>
            <a
              href="/docs/volaris-crypto/auditing"
              class="block py-2 px-4 rounded-lg hover:bg-purple-700 hover:bg-opacity-20 transition-colors duration-300"
            >
              Auditing
            </a>
          </div>
        </div>

        <a
          href="/docs/volaris-tools"
          class="flex items-center py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300"
        >
          <span class="material-icons text-lg mr-3">build_circle</span>
          <span>Volaris-Tools</span>
        </a>
        <a
          href="/docs/security-policy"
          class="flex items-center py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300"
        >
          <span class="material-icons text-lg mr-3">security</span>
          <span>Security Policy</span>
        </a>
        <a
          href="/docs/supporting-volaris"
          class="flex items-center py-3 px-4 rounded-lg hover:bg-purple-600 hover:bg-opacity-20 transition-colors duration-300"
        >
          <span class="material-icons text-lg mr-3">favorite</span>
          <span>Supporting Volaris</span>
        </a>
      </nav>
    </div>
  </aside>

  <main class={`flex-grow bg-gray-900 text-gray-100 p-8 overflow-y-auto ${sidebarOpen ? 'md:ml-72' : 'md:ml-0'}`}>
    <div class="content">
      <slot></slot>
    </div>
  </main>
</div>

<style global>
  @import url("https://fonts.googleapis.com/icon?family=Material+Icons");

  @media (max-width: 768px) {
    .fixed {
      position: fixed;
    }
    .translate-x-0 {
      transform: translateX(0);
    }
    .-translate-x-full {
      transform: translateX(-100%);
    }
  }
</style>
