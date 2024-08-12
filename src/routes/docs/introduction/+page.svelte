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
      <table class="min-w-full text-lg mb-6">
        <thead class="bg-pink-500 text-white">
          <tr>
            <th class="px-4 py-2">OS</th>
            <th class="px-4 py-2">Status</th>
          </tr>
        </thead>
        <tbody>
          <tr class="bg-gray-700">
            <td class="border px-4 py-2">Void Linux</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-800">
            <td class="border px-4 py-2">Fedora 35</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-700">
            <td class="border px-4 py-2">Fedora 36</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-800">
            <td class="border px-4 py-2">Fedora 39</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-700">
            <td class="border px-4 py-2">Fedora 40</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-800">
            <td class="border px-4 py-2">Ubuntu 20.04</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-700">
            <td class="border px-4 py-2">FreeBSD 13</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-800">
            <td class="border px-4 py-2">FreeBSD 14</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-700">
            <td class="border px-4 py-2">Windows 10</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-800">
            <td class="border px-4 py-2">Windows 11</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-700">
            <td class="border px-4 py-2">Android 14</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
          <tr class="bg-gray-800">
            <td class="border px-4 py-2">MacOS</td>
            <td class="border px-4 py-2">Yes</td>
          </tr>
        </tbody>
      </table>
    </section>

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
