<script>
// @ts-nocheck
	import "../app.css";
	import { Navbar, NavBrand, NavHamburger, NavUl, NavLi } from 'flowbite-svelte';
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
<Navbar let:hidden let:toggle color="primary">
	<NavBrand href="/">
	  <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-red-800">
		DANCING HEARTS
	  </span>
	</NavBrand>
	<NavHamburger on:click={toggle} />
	<NavUl {hidden}>
	  <NavLi href="/">Home</NavLi>
	  <NavLi href="/about">About</NavLi>
	  <!-- <NavLi href="/classes">Classes</NavLi> -->
	  <NavLi href="/events">Events</NavLi>
	  <NavLi href="/contact">Contact</NavLi>
	</NavUl>
</Navbar>
  
<!-- Slot for page-specific content -->
<!-- red-800 -->
<main class="bg-pink-100 p-4">
	<slot />
</main>