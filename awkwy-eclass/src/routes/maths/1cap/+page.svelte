<script>
    import { AccordionItem, Accordion } from 'flowbite-svelte';
    import { ChevronDoubleUpOutline, ChevronDoubleDownOutline } from 'flowbite-svelte-icons';
    import { Tabs, TabItem } from 'flowbite-svelte';
  </script>
  
 
  <svelte:head>
      <title>Mathématiques</title>
      <meta name="description" content="Mathématique premiere année cap" />
  </svelte:head>
  
  <main>
    <Accordion>
        <AccordionItem>
          <span slot="header">C'est quoi une statistique ?</span>
          <div slot="arrowup">
            <ChevronDoubleUpOutline class="h-6 w-6 -me-0.5" />
          </div>
          <span slot="arrowdown">
            <ChevronDoubleDownOutline class="h-6 w-6 -me-0.5" />
          </span>
          <Tabs tabStyle="full" defaultClass="flex rounded-lg divide-x rtl:divide-x-reverse divide-gray-200 shadow dark:divide-gray-700">
            <TabItem class="w-full" open>
              <span slot="title">notion</span>
              <p class="text-sm text-gray-500 dark:text-gray-400">
                <b>notion:</b>
                c'est une idée ou un petit morceau de connaisance qui aide à comprendre quelques chose.
              </p>
            </TabItem>
            <TabItem class="w-full">
              <span slot="title">Exemple</span>
              <p class="text-sm text-gray-500 dark:text-gray-400">
                <b>Exemple:</b>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
            </TabItem>
            <TabItem class="w-full">
              <span slot="title">cours</span>
              <p class="text-sm text-gray-500 dark:text-gray-400">
                <b>cours:</b>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
            </TabItem>
            <TabItem class="w-full">
              <span slot="title">Méthodes </span>
              <p class="text-sm text-gray-500 dark:text-gray-400">
                <b>Méthodes :</b>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
            </TabItem>
          </Tabs>
        </AccordionItem>
        <AccordionItem>
          <span slot="header">C'est quoi la proportionnalité ?</span>
          <div slot="arrowup">
            <ChevronDoubleUpOutline class="h-6 w-6 -me-0.5" />
          </div>
          <span slot="arrowdown">
            <ChevronDoubleDownOutline class="h-6 w-6 -me-0.5" />
          </span>

          <Tabs tabStyle="full" defaultClass="flex rounded-lg divide-x rtl:divide-x-reverse divide-gray-200 shadow dark:divide-gray-700">
            <TabItem class="w-full" open>
              <span slot="title">Notion</span>
              <p class="text-sm text-gray-500 dark:text-gray-400">
                <b>Notion:</b>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
            </TabItem>
            <TabItem class="w-full">
              <span slot="title">Exemple</span>
              <p class="text-sm text-gray-500 dark:text-gray-400">
                <b>Exemple:</b>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
            </TabItem>
            <TabItem class="w-full">
              <span slot="title">cours</span>
              <p class="text-sm text-gray-500 dark:text-gray-400">
                <b>cours:</b>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
            </TabItem>
            <TabItem class="w-full">
              <span slot="title">Méthodes </span>
              <p class="text-sm text-gray-500 dark:text-gray-400">
                <b>Méthodes :</b>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
            </TabItem>
          </Tabs>


        </AccordionItem>


        <AccordionItem>
            <span slot="header">C'est quoi une equation ?</span>
            <div slot="arrowup">
              <ChevronDoubleUpOutline class="h-6 w-6 -me-0.5" />
            </div>
            <span slot="arrowdown">
              <ChevronDoubleDownOutline class="h-6 w-6 -me-0.5" />
            </span>
            
            <Tabs tabStyle="full" defaultClass="flex rounded-lg divide-x rtl:divide-x-reverse divide-gray-200 shadow dark:divide-gray-700">
                <TabItem class="w-full" open>
                  <span slot="title">notion</span>
                  <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>notion:</b>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  </p>
                </TabItem>
                <TabItem class="w-full">
                  <span slot="title">Exemple</span>
                  <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Exemple:</b>
                    
                  </p>
                </TabItem>
                <TabItem class="w-full">
                  <span slot="title">cours</span>
                  <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>cours:</b>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  </p>
                </TabItem>
                <TabItem class="w-full">
                  <span slot="title">Méthodes </span>
                  <p class="text-sm text-gray-500 dark:text-gray-400">
                    <b>Méthodes :</b>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
                  </p>
                </TabItem>
              </Tabs>


          </AccordionItem>

          <AccordionItem>
            <span slot="header">C'est quoi une fonction?</span>
            <div slot="arrowup">
              <ChevronDoubleUpOutline class="h-6 w-6 -me-0.5" />
            </div>
            <span slot="arrowdown">
              <ChevronDoubleDownOutline class="h-6 w-6 -me-0.5" />
            </span>
            <p class="mb-2 text-gray-500 dark:text-gray-400">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Illo ab necessitatibus sint explicabo ...</p>
          </AccordionItem>




      </Accordion>
  </main>
  
  