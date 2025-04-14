<script>
// @ts-nocheck
	import "../app.css";
	import { Button, Alert, Card, Navbar, NavBrand, NavLi, NavUl, NavHamburger, Toast } from 'flowbite-svelte';
	import { FireOutline } from 'flowbite-svelte-icons';
	import { Gallery } from 'flowbite-svelte';
    import { ArrowRightOutline } from 'flowbite-svelte-icons';
	const image1 = {
		alt: 'erbology',
		src: 'https://flowbite.s3.amazonaws.com/docs/gallery/featured/image.jpg'
	};
	const images2 = [
		{ alt: 'shoes', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-1.jpg' },
		{ alt: 'small bag', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-2.jpg' },
		{ alt: 'plants', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-3.jpg' },
		{ alt: 'watch', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-4.jpg' },
		{ alt: 'shoe', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-5.jpg' }
	];
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
	  <NavLi href="src/routes/about">About</NavLi>
	  <NavLi href="/contact">Classes</NavLi>
	  <NavLi href="/events">Events</NavLi>
	  <NavLi href="/contact">Contact</NavLi>
	</NavUl>
</Navbar>
  
<div class="flex h-[calc(100vh-4rem)]"> <!-- adjust height to account for navbar -->
	<!-- Card section on the left -->
	<div class="w-1/2 p-8">
	  <Card>
		<h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">
		  <p>Dance.</p>
		  <p>Balance.</p>
		  <p>Passion.</p>
		</h5>
		<p class="mb-3 font-normal text-gray-700 dark:text-gray-400 leading-tight">
		  Dancing Hearts Dance Company
		</p>
		<Button as="a" href="/booking" class="w-fit">
		  BOOK NOW <ArrowRightOutline class="w-6 h-6 ms-2 text-white" />
		</Button>
	  </Card>
	</div>
  
	<!-- Gallery section on the right -->
	<div class="w-1/2 p-4 grid gap-4 bg-white/80 shadow-lg rounded-lg overflow-auto">
	  <img src={image1.src} alt={image1.alt} class="h-auto max-w-full rounded-lg" />
	  <Gallery class="grid-cols-5" items={images2} />
	</div>
  </div>