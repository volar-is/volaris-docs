<script>
    import "$lib/global.css";
    import { fade } from "svelte/transition";
    let openSections = {};
  
    function toggleSection(section) {
      openSections[section] = !openSections[section];
    }
  </script>
  
  <svelte:head>
    <title>Usage Examples</title>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </svelte:head>
  
  <div
    class="min-h-screen flex flex-col bg-gray-900 text-white px-4 py-8 sm:px-6 sm:py-10"
    transition:fade={{ duration: 250 }}
  >
    <div class="max-w-4xl mx-auto">
      <h1 class="text-4xl sm:text-5xl font-bold mb-12 text-center text-pink-500">
        Usage Examples
      </h1>
  
      <section class="mb-12">
        <h2 class="text-3xl font-semibold mb-6">Encrypting and Decrypting Files</h2>
        <p class="text-lg mb-6">
          Below are some common commands for encrypting and decrypting files using Dexios.
        </p>
        <ul class="list-disc list-inside text-lg mb-6 text-gray-300 space-y-4">
          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To just encrypt a file:</strong>
              {#if openSections['encrypt']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">dexios -e test.txt test.enc</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('encrypt')}
              aria-label="Toggle code"
            >
              {#if openSections['encrypt']}
                <span>&#9660;</span> 
              {:else}
                <span>&#9654;</span> 
              {/if}
            </button>
          </li>
  
          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To just decrypt a file:</strong>
              {#if openSections['decrypt']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">dexios -d test.enc test.txt</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('decrypt')}
              aria-label="Toggle code"
            >
              {#if openSections['decrypt']}
                <span>&#9660;</span> 
              {:else}
                <span>&#9654;</span> 
              {/if}
            </button>
          </li>

          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To just erase a file:</strong>
              {#if openSections['erase']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">dexios erase test.txt</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('erase')}
              aria-label="Toggle code"
            >
              {#if openSections['erase']}
                <span>&#9660;</span> 
              {:else}
                <span>&#9654;</span> 
              {/if}
            </button>
          </li>
  
          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To encrypt a file using AES-256-GCM (note: you do not need to specify <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">--aes</code> when decrypting):</strong>
              {#if openSections['aes']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">dexios -e --aes test.txt test.enc</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('aes')}
              aria-label="Toggle code"
            >
              {#if openSections['aes']}
                <span>&#9660;</span> 
              {:else}
                <span>&#9654;</span> 
              {/if}
            </button>
          </li>
  
          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To encrypt a file and show the hash of the encrypted file for verification later on:</strong>
              {#if openSections['hashEncrypt']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">dexios -eH test.txt test.enc</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('hashEncrypt')}
              aria-label="Toggle code"
            >
              {#if openSections['hashEncrypt']}
                <span>&#9660;</span> 
              {:else}
                <span>&#9654;</span> 
              {/if}
            </button>
          </li>
  
          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To decrypt a file and show the hash of the encrypted file (to compare with the hash generated above):</strong>
              {#if openSections['hashDecrypt']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">dexios -dH test.enc test.txt</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('hashDecrypt')}
              aria-label="Toggle code"
            >
              {#if openSections['hashDecrypt']}
                <span>&#9660;</span> 
              {:else}
                <span>&#9654;</span> 
              {/if}
            </button>
          </li>
  
          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To encrypt a file and erase the original file:</strong>
              {#if openSections['encryptErase']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">dexios -e --erase test.txt test.enc</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('encryptErase')}
              aria-label="Toggle code"
            >
              {#if openSections['encryptErase']}
                <span>&#9660;</span> 
              {:else}
                <span>&#9654;</span> 
              {/if}
            </button>
          </li>
  
          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To use a keyfile for encryption:</strong>
              {#if openSections['keyfile']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">dexios -ek keyfile test.txt test.enc</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('keyfile')}
              aria-label="Toggle code"
            >
              {#if openSections['keyfile']}
                <span>&#9660;</span> 
              {:else}
                <span>&#9654;</span> 
              {/if}
            </button>
          </li>
  
          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To encrypt all .mp4 files in a directory (using find):</strong> Remove <code class="text-pink-500 bg-gray-800 rounded px-2 py-1">-maxdepth 1</code> to make this run recursively
              {#if openSections['encryptAll']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">find *.mp4 -type f -maxdepth 1 -exec dexios -eyk keyfile &lbrace;&rbrace; &lbrace;&rbrace;.enc \;</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('encryptAll')}
              aria-label="Toggle code"
            >
              {#if openSections['encryptAll']}
                <span>&#9660;</span> 
              {:else}
                <span>&#9654;</span> 
              {/if}
            </button>
          </li>
  

          <li class="flex flex-col sm:flex-row items-start space-y-2 sm:space-y-0 sm:space-x-4">
            <div class="flex-1">
              <strong>To decrypt all .mp4.enc files in a directory and remove the .enc suffix:</strong>
              {#if openSections['decryptAll']}
                <pre class="bg-gray-800 p-4 rounded-lg mt-2 overflow-x-auto">
                  <code class="text-pink-400">find . -type f -iname "*.mp4.enc" -exec sh -c 'dexios -dk keyfile "$0" "$&lbrace;0%.enc}"' &lbrace;&rbrace; \;</code>
                </pre>
              {/if}
            </div>
            <button
              class="text-pink-500 bg-gray-800 hover:bg-gray-700 p-2 rounded"
              on:click={() => toggleSection('decryptAll')}
              aria-label="Toggle code"
            >
              {#if openSections['decryptAll']}
                <span>&#9660;</span>
              {:else}
                <span>&#9654;</span>
              {/if}
            </button>
          </li>
        </ul>
      </section>
  
      <div class="flex justify-between items-center mt-16">
        <a
          href="/docs/environment-variables"
          class="bg-pink-600 text-white font-semibold py-3 px-6 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
        >
          Previous
        </a>
        <a
          href="/docs/privacy"
          class="bg-pink-600 text-white font-semibold py-3 px-6 rounded-lg shadow-md hover:bg-pink-500 transition duration-300"
        >
          Next
        </a>
      </div>
    </div>
  </div>
  