<script>
// @ts-nocheck
	import "../app.css";
	import { DarkMode } from 'flowbite-svelte';
	import { Navbar, NavBrand, NavHamburger, NavUl, NavLi } from 'flowbite-svelte';
	import { HeartOutline } from 'flowbite-svelte-icons'
	const image1 = {
		alt: 'logo',
		src: '/images/dh_logo.jpeg'
	};
	const images2 = [
		{ alt: 'pic_blue', src: '/images/image_blue.jpeg' },
		{ alt: 'pic_red', src: '/images/image_red.jpeg' },
		{ alt: 'pic_black', src: '/images/image_black.jpeg' },
	];
	const videos = [
		{ alt: 'vid_1', src: '/videos/video-1.mp4' },
		{ alt: 'vid_2', src: '/videos/video-2.mp4' }
  	];
	let current = 0;

	function next() {
		current = (current + 1) % videos.length;
	}

	function prev() {
		current = (current - 1 + videos.length) % videos.length;
	}
</script>
  
<!-- Navbar stays on top -->
<Navbar let:hidden let:toggle class="bg-white dark:bg-red-400">
	<NavBrand href="/">
	  <span class="self-center whitespace-nowrap text-2xl font-semibold text-red-400 dark:text-white">
		<p class="flex items-center">
		DANCING HEARTS 
		<HeartOutline class="w-6 h-6 ms-2 text-red-400 dark:text-white " />
		</p>
	  </span>
	</NavBrand>
	<NavHamburger on:click={toggle} />
	<NavUl {hidden}>
	  <NavLi href="/" class="text-base text-gray-800 dark:text-white hover:!text-red-400 dark:hover:!text-gray-300">Home</NavLi>
	  <NavLi href="/about" class="text-base text-gray-800 dark:text-white hover:!text-red-400 dark:hover:!text-gray-300">About</NavLi>
	  <!-- <NavLi href="/classes">Classes</NavLi> -->
	  <NavLi href="/services" class="text-base text-gray-800 dark:text-white hover:!text-red-400 dark:hover:!text-gray-300">Services</NavLi>
	  <NavLi href="/gallery" class="text-base text-gray-800 dark:text-white hover:!text-red-400 dark:hover:!text-gray-300">Gallery</NavLi>
	  <NavLi href="/contact" class="text-base text-gray-800 dark:text-white hover:!text-red-400 dark:hover:!text-gray-300">Contact</NavLi>
	  <NavLi>
		<DarkMode class="text-gray-800 dark:text-white border-white dark:border-gray-800 -mt-[8px]" />
	  </NavLi> 
	</NavUl>
</Navbar>
  
<!-- Slot for page-specific content -->
<!-- red-800 -->
<main class="bg-red-400 dark:bg-gray-800 p-4">
	<slot />
</main>