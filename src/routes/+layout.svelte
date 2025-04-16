<script>
// @ts-nocheck
	import "../app.css";
	import { Button, Alert, Card, Navbar, NavBrand, NavLi, NavUl, NavHamburger, Toast } from 'flowbite-svelte';
	import { FireOutline, CaretRightSolid, CaretLeftSolid } from 'flowbite-svelte-icons';
	import { Gallery } from 'flowbite-svelte';
    import { ArrowRightOutline } from 'flowbite-svelte-icons';
	import { Carousel } from 'flowbite-svelte';
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
		  Dancing Hearts Dance Company...
		</p>
		<Button as="a" href="/contact" class="w-fit">
		  BOOK NOW <ArrowRightOutline class="w-6 h-6 ms-2 text-white" />
		</Button>
	  </Card>
	</div>
  
	<!-- Gallery section on the right -->
	<div class="w-1/2 p-4 bg-white/80 shadow-lg rounded-lg">
		<div class="grid grid-cols-2 gap-4 mb-4">
			<!-- Top left: Logo -->
			<div>
				<img src={image1.src} alt={image1.alt} class="w-full h-auto rounded-lg" />
			</div>

			<div class="relative w-[300px] aspect-[7/10] mx-auto">
				{#each videos as video, index}
					<div class={`absolute inset-0 transition-opacity duration-500 ${index === current ? 'opacity-100 z-10' : 'opacity-0 z-0'}`}>
						<!-- svelte-ignore element_invalid_self_closing_tag -->
						<video
							src={video.src}
							autoplay
							muted
							loop
							playsinline
							class="w-full h-full object-cover rounded-lg"
						/>
					</div>
				{/each}
			
				<!-- Controls -->
				<!-- Arrows -->
				<button
					on:click={prev}
					class="absolute top-1/2 left-2 -translate-y-1/2 text-white bg-black/40 rounded-full p-2 hover:bg-black/60 z-20"
				>
					<CaretLeftSolid class="w-5 h-5" />
				</button>

				<button
					on:click={next}
					class="absolute top-1/2 right-2 -translate-y-1/2 text-white bg-black/40 rounded-full p-2 hover:bg-black/60 z-20"
				>
					<CaretRightSolid class="w-5 h-5" />
				</button>
			</div>
		</div>

		<!-- Bottom row: Three images side by side -->
		<div class="grid grid-cols-3 gap-4">
			<img src={images2[0].src} alt={images2[0].alt} class="w-full h-auto rounded-lg" />
			<img src={images2[1].src} alt={images2[1].alt} class="w-full h-auto rounded-lg" />
			<img src={images2[2].src} alt={images2[2].alt} class="w-full h-auto rounded-lg" />
		</div>
	</div>
</div>