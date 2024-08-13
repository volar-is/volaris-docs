<script>
  import { fade } from "svelte/transition";
  import '$lib/global.css';
</script>

<svelte:head>
  <title>Volaris Documentation</title>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<div
  class="min-h-screen flex flex-col bg-gray-900 text-white px-4 py-8 "
  transition:fade={{ duration: 250 }}
>
  <div class="max-w-4xl mx-auto">
    <h1 class="text-4xl sm:text-5xl font-extrabold mb-8 text-center text-transparent bg-clip-text bg-gradient-to-r from-pink-500 to-purple-500">
      Welcome to the Volaris Documentation
    </h1>
    <h3 class="font-medium mb-6 text-center text-gray-400">
      Note: This documentation is mainly for developers and CLI users of Volaris.
    </h3>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">Introduction</h2>
      <p class="text-lg mb-6 text-gray-300">
        Welcome to the Volaris Documentation! Here you'll find comprehensive
        information about Volaris, including how to use it, best practices,
        performance metrics, and more. Navigate through the sections to explore
        detailed guides and resources.
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">What is Volaris?</h2>
      <p class="text-lg mb-6 text-gray-300">
        Volaris is a robust command-line file encryption utility designed for
        securing files before uploading them to cloud services. Built entirely
        in Rust, Volaris ensures safety by avoiding unsafe code (note that some
        dependencies might have undergone rigorous security audits).
      </p>
      <p class="text-lg mb-6 text-gray-300">
        By default, Volaris employs XChaCha20-Poly1305 encryption. You can opt
        for AES-256-GCM by using the <code class="text-pink-500 bg-gray-800 px-2 py-1 rounded">--aes</code> flag.
      </p>
      <p class="text-lg mb-6 text-gray-300">
        For hashing passwords, Volaris uses BLAKE3-Balloon by default.
        Alternatively, you can use argon2id for key hashing by specifying <code
          class="text-pink-500 bg-gray-800 px-2 py-1 rounded">--argon</code
        > during encryption.
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">Security Notices</h2>
      <p class="text-lg mb-6 text-gray-300">
        The AES-GCM crate has been audited by NCC Group with no significant
        findings. You can review the audit <a
          href="https://research.nccgroup.com/2020/02/26/public-report-rustcrypto-aes-gcm-and-chacha20poly1305-implementation-review/"
          class="text-pink-400 font-bold hover:text-pink-300 transition-colors duration-200">here</a
        >.
      </p>
      <p class="text-lg mb-6 text-gray-300">
        Similarly, the ChaCha20-Poly1305 crate has undergone an NCC Group
        security audit with no notable issues. View the audit <a
          href="https://research.nccgroup.com/2020/02/26/public-report-rustcrypto-aes-gcm-and-chacha20poly1305-implementation-review/"
          class="text-pink-400 font-bold hover:text-pink-300 transition-colors duration-200">here</a
        >.
      </p>
      <p class="text-lg mb-6 text-gray-300">BLAKE3-Balloon is used for password hashing.</p>
      <p class="text-lg mb-6 text-gray-300">
        All other cryptographic functions are considered secure, though they do
        not directly protect your data. Therefore, vulnerabilities in these
        functions would not compromise the security of your encrypted data.
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">Default Settings</h2>
      <p class="text-lg mb-6 text-gray-300">
        Volaris defaults are designed to meet the needs of even the most
        security-conscious users.
      </p>
      <p class="text-lg mb-6 text-gray-300">
        By executing the command <code class="text-pink-500 bg-gray-800 px-2 py-1 rounded">volaris-cli -e input.txt output.enc</code>, you are utilizing the following security features:
      </p>
      <ul class="list-disc list-inside text-lg mb-6 text-gray-300">
        <li>XChaCha20-Poly1305 encryption</li>
        <li>BLAKE3-Balloon hashing</li>
        <li>Complete erasure of sensitive data from memory</li>
        <li>
          A tamper-evident header authenticated with each block of encrypted
          data
        </li>
        <li>LE31 STREAM encryption</li>
      </ul>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">Tested Operating Systems</h2>
      <div class="overflow-hidden rounded-lg shadow-lg border border-gray-700">
        <table class="min-w-full text-lg">
          <thead class="bg-gradient-to-r from-pink-500 to-purple-500 text-white">
            <tr>
              <th class="px-6 py-3 text-left">OS</th>
              <th class="px-6 py-3 text-left">Notes</th>
            </tr>
          </thead>
          <tbody class="divide-y divide-gray-600">
            <tr class="bg-gray-700 odd:bg-gray-800 hover:bg-gray-600 transition-colors duration-200 cursor-pointer" onclick="openModal('void-linux')">
              <td class="px-6 py-4">Void Linux</td>
              <td class="px-6 py-4">All known to be working</td>
            </tr>
            <tr class="bg-gray-800 odd:bg-gray-700 hover:bg-gray-600 transition-colors duration-200 cursor-pointer" onclick="openModal('fedora-35')">
              <td class="px-6 py-4">Fedora 35</td>
              <td class="px-6 py-4">Fedora 35 and up</td>
            </tr>
            <tr class="bg-gray-700 odd:bg-gray-800 hover:bg-gray-600 transition-colors duration-200 cursor-pointer" onclick="openModal('ubuntu-20.04')">
              <td class="px-6 py-4">Ubuntu 20.04</td>
              <td class="px-6 py-4">Ubuntu 20.04 and up</td>
            </tr>
            <tr class="bg-gray-800 odd:bg-gray-700 hover:bg-gray-600 transition-colors duration-200 cursor-pointer" onclick="openModal('freebsd-13')">
              <td class="px-6 py-4">FreeBSD 13</td>
              <td class="px-6 py-4">FreeBSD 13 and up</td>
            </tr>
            <tr class="bg-gray-700 odd:bg-gray-800 hover:bg-gray-600 transition-colors duration-200 cursor-pointer" onclick="openModal('windows-10')">
              <td class="px-6 py-4">Windows 10</td>
              <td class="px-6 py-4">Windows 10 and up</td>
            </tr>
            <tr class="bg-gray-800 odd:bg-gray-700 hover:bg-gray-600 transition-colors duration-200 cursor-pointer" onclick="openModal('android-12')">
              <td class="px-6 py-4">Android 12</td>
              <td class="px-6 py-4">Android 12 and up</td>
            </tr>
            <tr class="bg-gray-700 odd:bg-gray-800 hover:bg-gray-600 transition-colors duration-200 cursor-pointer" onclick="openModal('macos')">
              <td class="px-6 py-4">MacOS</td>
              <td class="px-6 py-4">Big Sur and up</td>
            </tr>
            <tr class="bg-gray-800 odd:bg-gray-700 hover:bg-gray-600 transition-colors duration-200 cursor-pointer" onclick="openModal('other')">
              <td class="px-6 py-4">Other</td>
              <td class="px-6 py-4">Above are all officially known to work, but other OS's may work.</td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>

    <div id="void-linux" class="fixed inset-0 bg-gray-900 bg-opacity-75 flex justify-center items-center hidden">
      <div class="bg-gray-800 rounded-lg shadow-lg p-8 text-white max-w-lg">
        <h3 class="text-2xl font-semibold mb-4">Void Linux Compatibility</h3>
        <p class="mb-4">Void Linux is fully supported with all known configurations working smoothly.</p>
        <button class="bg-pink-500 hover:bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg" onclick="closeModal('void-linux')">Close</button>
      </div>
    </div>
    
    <div id="fedora-35" class="fixed inset-0 bg-gray-900 bg-opacity-75 flex justify-center items-center hidden">
      <div class="bg-gray-800 rounded-lg shadow-lg p-8 text-white max-w-lg">
        <h3 class="text-2xl font-semibold mb-4">Fedora 35 Compatibility</h3>
        <p class="mb-4">Fedora 35 and all subsequent versions are officially supported.</p>
        <button class="bg-pink-500 hover:bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg" onclick="closeModal('fedora-35')">Close</button>
      </div>
    </div>
    
    <div id="ubuntu-20.04" class="fixed inset-0 bg-gray-900 bg-opacity-75 flex justify-center items-center hidden">
      <div class="bg-gray-800 rounded-lg shadow-lg p-8 text-white max-w-lg">
        <h3 class="text-2xl font-semibold mb-4">Ubuntu 20.04 Compatibility</h3>
        <p class="mb-4">Ubuntu 20.04 and later versions are supported with all known issues resolved.</p>
        <button class="bg-pink-500 hover:bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg" onclick="closeModal('ubuntu-20.04')">Close</button>
      </div>
    </div>
    
    <div id="freebsd-13" class="fixed inset-0 bg-gray-900 bg-opacity-75 flex justify-center items-center hidden">
      <div class="bg-gray-800 rounded-lg shadow-lg p-8 text-white max-w-lg">
        <h3 class="text-2xl font-semibold mb-4">FreeBSD 13 Compatibility</h3>
        <p class="mb-4">FreeBSD 13 and newer versions are officially supported.</p>
        <button class="bg-pink-500 hover:bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg" onclick="closeModal('freebsd-13')">Close</button>
      </div>
    </div>
    
    <div id="windows-10" class="fixed inset-0 bg-gray-900 bg-opacity-75 flex justify-center items-center hidden">
      <div class="bg-gray-800 rounded-lg shadow-lg p-8 text-white max-w-lg">
        <h3 class="text-2xl font-semibold mb-4">Windows 10 Compatibility</h3>
        <p class="mb-4">Windows 10 and up are fully supported with no known issues.</p>
        <button class="bg-pink-500 hover:bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg" onclick="closeModal('windows-10')">Close</button>
      </div>
    </div>
    
    <div id="android-12" class="fixed inset-0 bg-gray-900 bg-opacity-75 flex justify-center items-center hidden">
      <div class="bg-gray-800 rounded-lg shadow-lg p-8 text-white max-w-lg">
        <h3 class="text-2xl font-semibold mb-4">Android 12 Compatibility</h3>
        <p class="mb-4">Android 12 and later versions are supported, but performance may vary depending on device hardware. Due to the nature of android being a mobile OS, please follow the install instructions on <a href="/docs/installing-building#android" class="text-pink-400 font-bold hover:text-pink-300 transition-colors duration-200">the installing page.</a></p>
        <button class="bg-pink-500 hover:bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg" onclick="closeModal('android-12')">Close</button>
      </div>
    </div>
    
    <div id="macos" class="fixed inset-0 bg-gray-900 bg-opacity-75 flex justify-center items-center hidden">
      <div class="bg-gray-800 rounded-lg shadow-lg p-8 text-white max-w-lg">
        <h3 class="text-2xl font-semibold mb-4">MacOS Compatibility</h3>
        <p class="mb-4">MacOS Big Sur and later versions are fully supported.</p>
        <button class="bg-pink-500 hover:bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg" onclick="closeModal('macos')">Close</button>
      </div>
    </div>
    
    <div id="other" class="fixed inset-0 bg-gray-900 bg-opacity-75 flex justify-center items-center hidden">
      <div class="bg-gray-800 rounded-lg shadow-lg p-8 text-white max-w-lg">
        <h3 class="text-2xl font-semibold mb-4">Other OS Compatibility</h3>
        <p class="mb-4">While other OS's may work, only the ones listed are officially supported.</p>
        <button class="bg-pink-500 hover:bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg" onclick="closeModal('other')">Close</button>
      </div>
    </div>
    
    <script>
      function openModal(id) {
        document.getElementById(id).classList.remove('hidden');
      }
    
      function closeModal(id) {
        document.getElementById(id).classList.add('hidden');
      }
    </script>
    
    

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">Privacy</h2>
      <p class="text-lg mb-6 text-gray-300">
        Volaris is committed to user privacy. No data is collected, transmitted,
        or sent to any external servers.
      </p>
      <p class="text-lg mb-6 text-gray-300">
        All operations occur locally on your hardware, ensuring complete
        privacy.
      </p>
      <p class="text-lg mb-6 text-gray-300">
        We encourage users to review the source code to verify our privacy
        practices.
      </p>
      <p class="text-lg mb-6 text-gray-300">
        The cryptographic functions can be found in the <a
          href="https://github.com/volar-is/volaris/tree/main/crates/volaris-crypto"
          class="text-pink-400 font-bold hover:text-pink-300 transition-colors duration-200">volaris-crypto</a
        > repository.
      </p>
    </section>

    <section>
      <h2 class="text-3xl font-semibold mb-4 ">Thank You!</h2>
      <p class="text-lg mb-6 text-gray-300">
        A heartfelt thank you to the RustCrypto Team for their invaluable
        contributions to the Rust cryptography ecosystem. Volaris would not be
        possible without their dedication and hard work.
      </p>
    </section>
  </div>

  <div class="flex justify-between items-center mt-12">
    <div></div>
    <a
      href="/docs/installing-building"
      class="bg-gradient-to-r from-pink-500 to-purple-500 text-white font-semibold py-2 px-4 rounded-lg shadow-lg hover:from-pink-600 hover:to-purple-600 transition duration-300 transform hover:scale-105"
    >
      Next
    </a>
  </div>
</div>
