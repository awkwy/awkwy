<script>
  import { Card } from 'flowbite-svelte';
  import Flex from 'svelte-flex';
</script>

<svelte:head>
	<title>cours</title>
	<meta name="description" content="cours de l'année 2024" />
</svelte:head>

<main>
	<Flex>
		<div>
			<Card href="/classe-1cap">
				<h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Premiere CAP MIS/CAN</h5>
				<p class="font-normal text-gray-700 dark:text-gray-400 leading-tight">Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.</p>
			  </Card>
		</div>
		<div>
			<Card href="/classe-1tp">
				<h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Premiere Travaux Public</h5>
				<p class="font-normal text-gray-700 dark:text-gray-400 leading-tight">Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.</p>
			  </Card>
		</div>
		<div>
			<Card href="/classe-ttp">
				<h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Terminal Travaux Public</h5>
				<p class="font-normal text-gray-700 dark:text-gray-400 leading-tight">Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.</p>
			  </Card>
		</div>
	  </Flex>
</main>
