<!-- src/routes/+page.svelte -->
<script>
// @ts-nocheck

  import { onMount } from 'svelte';
  import { Button, Card, Carousel } from 'flowbite-svelte';
  import { ArrowRightOutline, CaretLeftSolid, CaretRightSolid } from 'flowbite-svelte-icons';

  // Image and video data
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
    { alt: 'vid_1', src: '/videos/emry.MP4' },
    { alt: 'vid_2', src: '/videos/jocelynn.MP4' },
    { alt: 'vid_2', src: '/videos/khalani.MP4' }
  ];
  
  let current = 0;

  function next() {
    current = (current + 1) % videos.length;
  }

  function prev() {
    current = (current - 1 + videos.length) % videos.length;
  }

  const testimonials = [
    {
      name: "Sophia M.",
      quote: "Dancing Hearts brought so much joy to our wedding. Highly recommended!",
    },
    {
      name: "Carlos G.",
      quote: "Their team made my Quince unforgettable! I felt so confident dancing!",
    },
    {
      name: "Alyssa T.",
      quote: "The private lessons were a game changer. They taught me with so much patience and love!",
    }
  ];
  let curr = 0;
  let interval;

  // Manually switch to a specific testimonial
  const goToTestimonial = (index) => {
    curr = index;
  };
</script>
  
<div class="flex flex-col md:flex-row h-auto md:h-[calc(100vh-7rem)] px-4 md:px-12 gap-6">
  <!-- Card section on the left -->
  <div class="w-full md:w-1/2 p-4 md:p-8">
    <Card class="dark:bg-red-400">
      <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">
        <p>Dance.</p>
        <p>Balance.</p>
        <p>Passion.</p>
      </h5>
      <!-- <p class="mb-3 font-normal text-gray-700 dark:text-gray-400 leading-tight">
        Dancing Hearts Dance Company...
      </p> -->
      <Button as="a" href="/contact" class="w-fit dark:bg-gray-800">
        BOOK NOW <ArrowRightOutline class="w-6 h-6 ms-2 text-white" />
      </Button>
    </Card>

    {#if testimonials && testimonials.length > 0}
      <!--125-->
      <div class="mt-10">
        <Card class="p-6 text-center dark:bg-red-400 w-full h-40 mx-auto relative ml-0">
          <h5 class="mb-2 text-xl font-semibold text-gray-900 dark:text-white">
            {testimonials[curr].name}
          </h5>
          <p class="text-gray-700 dark:text-white italic">"{testimonials[curr].quote}"</p>
    
          <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex space-x-2">
            {#each testimonials as _, index}
              <!-- svelte-ignore a11y_consider_explicit_label -->
              <button
                class={`w-3 h-3 rounded-full transition-all ${curr === index ? 'bg-black' : 'bg-gray-300'}`}
                on:click={() => goToTestimonial(index)}
              ></button>
            {/each}
          </div>
        </Card>
      </div>
    {:else}
      <p class="text-center text-gray-500 dark:text-white">No testimonials yet!</p>
    {/if}
  </div>

  <!-- Gallery section on the right -->
  <div class="w-full md:w-1/2 p-4 bg-white dark:bg-red-400 shadow-lg rounded-lg">
    <div class="grid grid-cols-2 gap-4 mb-20">
      <!-- Top left: Logo -->
      <div>
        <img src={image1.src} alt={image1.alt} class="w-full h-auto rounded-lg shadow-md" />
      </div>

      <div class="relative w-full max-w-[300px] aspect-[7/10] mx-auto">
        {#each videos as video, index}
          <div class={`absolute inset-0 transition-opacity duration-500 ${index === current ? 'opacity-100 z-10' : 'opacity-0 z-0'}`}>
              <!-- svelte-ignore element_invalid_self_closing_tag -->
              <video
                  key={index}
                  src={video.src}
                  autoplay
                  muted
                  loop
                  playsinline
                  class="w-full h-full object-cover rounded-lg shadow-md"
                  on:loadedmetadata={(event) => {
                  // Reset video playback time to 0 when video is loaded
                  event.target.currentTime = 0;
                  }}
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
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4">
      <img src={images2[0].src} alt={images2[0].alt} class="w-full h-auto rounded-lg shadow-md" />
      <img src={images2[1].src} alt={images2[1].alt} class="w-full h-auto rounded-lg shadow-md" />
      <img src={images2[2].src} alt={images2[2].alt} class="w-full h-auto rounded-lg shadow-md" />
    </div>
  </div>
</div>