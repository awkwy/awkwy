<script>
    import { Card } from 'flowbite-svelte';
    import Flex from 'svelte-flex';
  </script>
  
  <svelte:head>
      <title>Mathématiques</title>
      <meta name="description" content="Mathématique premiere bac pro" />
  </svelte:head>
  
  <main>
      <Flex>
          <div>
              <Card href="/cards">
                  <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Math</h5>
                  <p class="font-normal text-gray-700 dark:text-gray-400 leading-tight">Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.</p>
                </Card>
          </div>
          <div>
              <Card href="/cards">
                  <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Sciences</h5>
                  <p class="font-normal text-gray-700 dark:text-gray-400 leading-tight">Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.</p>
                </Card>
          </div>
          
        </Flex>
      
      
  </main>
  
  