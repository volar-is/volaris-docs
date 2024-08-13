<script>
  import "$lib/global.css";
  import { fade } from "svelte/transition";
</script>

<svelte:head>
  <title>Installing Volaris</title>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</svelte:head>

<div
  class="min-h-screen flex flex-col text-white px-4 py-8"
  transition:fade={{ duration: 250 }}
>
  <div class="max-w-4xl mx-auto">
    <h1 class="text-4xl sm:text-5xl font-bold mb-8 text-center text-pink-500">
      Installing Volaris
    </h1>

    <section class="mb-12">
      <p class="text-lg mb-6">
        To install Volaris, there are two main options.
      </p>
      <p class="text-lg mb-6">
        Firstly, you can install via Cargo with 
        <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">cargo install volaris-cli</code>, 
        or you may download a binary from the 
        <a
          href="https://github.com/volar-is/volaris/releases/latest"
          class="text-pink-500 underline hover:text-pink-400"
          >release</a
        > page (make sure you mark it as executable, otherwise it won't run!).
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4 text-pink-400">Linux/FreeBSD</h2>
      <p class="text-lg mb-6">
        To use Cargo for installing, ensure you have GCC installed on your
        system.
      </p>
      <p class="text-lg mb-6">
        You may install via Cargo with the command 
        <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">cargo install volaris-cli</code>.
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4 text-pink-400">Windows</h2>
      <p class="text-lg mb-6">
        You may also use Cargo for installing, just run the command:
      </p>
      <p class="text-lg mb-6">
        <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">cargo install volaris-cli</code>
      </p>
    </section>

    <section class="mb-12" id="android">
      <h2 class="text-3xl font-semibold mb-4 text-pink-400">Android</h2>
      <p class="text-lg mb-6">
        Volaris can be installed on Android devices via Termux. All features
        have been confirmed to work, but if you find any issues, please open a GitHub
        issue.
      </p>
      <p class="text-lg mb-6">
        Volaris was tested on Android 14 with Termux v0.129, but it should work
        on a wide range of devices.
      </p>
      <p class="text-lg mb-6">
        To install, ensure you have Cargo installed. You may install Volaris
        with the command:
      </p>
      <p class="text-lg mb-6">
        <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">AR=llvm-ar cargo install volaris-cli</code>
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4 text-pink-400">Building Notes</h2>
      <p class="text-lg mb-6">
        GCC is required for building on Linux and FreeBSD.
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4 text-pink-400">
        Downloading and Running a Pre-Compiled Binary
      </h2>
      <p class="text-lg mb-6">
        The GitHub Releases page contains pre-compiled binaries, generated with
        GitHub Actions. These are ideal if you don't want to go through the
        hassle of building, and they should run on any system (provided the
        architecture matches). They are the exact same binaries from GitHub
        Actions, so we can ensure they haven't been tampered with.
      </p>
      <p class="text-lg mb-6">
        We encourage users to check the hash provided in the GA Workflow, and
        compare it with the file you have downloaded.
      </p>
    </section>
  </div>

  <div class="flex justify-between items-center mt-12">
    <a
      href="/docs/introduction"
      class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
    >
      Previous
    </a>
    <a
      href="/docs/choosing-key"
      class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
    >
      Next
    </a>
  </div>
</div>
