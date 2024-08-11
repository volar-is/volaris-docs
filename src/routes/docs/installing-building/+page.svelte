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
  class="min-h-screen flex flex-col bg-gray-900 text-white px-4 py-8"
  transition:fade={{ duration: 250 }}
>
  <div class="max-w-4xl mx-auto">
    <h1 class="text-4xl sm:text-5xl font-bold mb-8 text-center">
      Installing Volaris
    </h1>

    <section class="mb-12">
      <p class="text-lg mb-6">
        To install Volaris, there are two main options.
      </p>
      <p class="text-lg mb-6">
        Firstly, you can install via cargo with <code class="text-pink-500"
          >cargo install volaris-cli</code
        >, or you may download a binary from the release page (make sure you
        mark it as executable, otherwise it won't run!).
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">Linux/FreeBSD</h2>
      <p class="text-lg mb-6">
        To use cargo for installing, ensure you have gcc installed on your
        system.
      </p>
      <p class="text-lg mb-6">
        You may install via cargo with the command <code class="text-pink-500"
          >cargo install volaris-cli</code
        >
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">Windows</h2>
      <p class="text-lg mb-6">
        You may also use cargo for installing, just run the command:
      </p>
      <p class="text-lg mb-6">
        <code class="text-pink-500">cargo install volaris-cli</code>
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">Android</h2>
      <p class="text-lg mb-6">
        Volaris can be installed on Android devices, via Termux. All features
        have been confirmed to work, but if you find any, please open a Github
        issue.
      </p>
      <p class="text-lg mb-6">
        Volaris was tested on Android 12, with Termux v0.118.0, but it should
        work on a wide range of devices.
      </p>
      <p class="text-lg mb-6">
        To install, ensure you have cargo installed. You may install Volaris
        with the command:
      </p>
      <p class="text-lg mb-6">
        <code class="text-pink-500">AR=llvm-ar cargo install volaris-cli</code>
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">Building Notes</h2>
      <p class="text-lg mb-6">
        gcc is required for building on Linux and FreeBSD.
      </p>
    </section>

    <section class="mb-12">
      <h2 class="text-3xl font-semibold mb-4">
        Downloading and Running a Pre-Compiled Binary
      </h2>
      <p class="text-lg mb-6">
        The Github Releases page contains pre-compiled binaries, generated with
        Github Actions. These are ideal if you don't want to go through the
        hassle of building, and they should run on any system (provided the
        architecture matches). They are the exact same binaries from Github
        Actions, so we can ensure they haven't been tampered with.
      </p>
      <p class="text-lg mb-6">
        We encourage users to check the hash provided in the GA Workflow, and
        compare with the file you have downloaded.
      </p>
    </section>
  </div>

  <div class="flex justify-between items-center mt-12">
    <a
      href="/introduction"
      class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
    >
      Previous
    </a>
    <a
      href="/choosing-key"
      class="bg-pink-600 text-white font-semibold py-2 px-4 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
    >
      Next
    </a>
  </div>
</div>
