<script>
	import '../app.css';
	import { page } from '$app/stores';
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger} from 'flowbite-svelte';
	$: activeUrl = $page.url.pathname;
</script>

<html class="dark" lang="en"></html>
<Navbar  >
	<NavBrand href="/">
	  <img src="/Users/yurij/Documents/GitHub/awkwy/awkwy-eclass/static/Logo-eclass.png" class="me-3 h-6 sm:h-9" alt="Logo" />
	  <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Flowbite</span>
	</NavBrand>
	<NavHamburger  />
	<NavUl >
	  <NavLi href="/">Home</NavLi>
	  <NavLi href="/about">About</NavLi>
	  <NavLi href="/docs/components/navbar">Navbar</NavLi>
	  <NavLi href="/pricing">Pricing</NavLi>
	  <NavLi href="/contact">Contact</NavLi>
	</NavUl>
  </Navbar>
<main>
	<slot></slot>
</main>
