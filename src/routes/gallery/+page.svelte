<script>
    import { CaretLeftSolid, CaretRightSolid } from 'flowbite-svelte-icons';
  
    const images = [
      { src: '/images/carousel/photo1.PNG', alt: 'Dance image 1' },
      { src: '/images/carousel/photo2.PNG', alt: 'Dance image 2' },
      { src: '/images/carousel/photo3.PNG', alt: 'Dance image 3' },
      { src: '/images/carousel/photo4.PNG', alt: 'Dance image 4' },
      { src: '/images/carousel/photo5.PNG', alt: 'Dance image 5' },
      { src: '/images/carousel/photo6.PNG', alt: 'Dance image 6' },
      { src: '/images/carousel/photo7.PNG', alt: 'Dance image 7' },
      { src: '/images/carousel/photo8.PNG', alt: 'Dance image 8' },
      { src: '/images/carousel/photo9.PNG', alt: 'Dance image 9' },
      { src: '/images/carousel/photo10.PNG', alt: 'Dance image 10' },
      { src: '/images/carousel/photo11.PNG', alt: 'Dance image 11' },
      { src: '/images/carousel/photo12.PNG', alt: 'Dance image 12' },
      { src: '/images/carousel/photo13.PNG', alt: 'Dance image 13' },
      { src: '/images/carousel/photo14.PNG', alt: 'Dance image 14' },
      { src: '/images/carousel/photo15.PNG', alt: 'Dance image 15' },
      { src: '/images/carousel/photo16.PNG', alt: 'Dance image 16' },
      { src: '/images/carousel/photo17.PNG', alt: 'Dance image 17' },
      { src: '/images/carousel/photo18.PNG', alt: 'Dance image 18' }
    ];

    let currentIndex = 0;

    function nextImage() {
        currentIndex = (currentIndex + 1) % images.length;
    }

    function prevImage() {
        currentIndex = (currentIndex - 1 + images.length) % images.length;
    }
</script>

<div class="carousel-container w-full max-w-[1280px] mx-auto px-4 relative">
  <!-- Image Display -->
  <div class="w-full h-[50vh] sm:h-[60vh] md:h-[70vh] lg:h-[80vh] overflow-hidden relative rounded-lg shadow-lg">
    {#each images as image, index}
      <img
        src={image.src}
        alt={image.alt}
        class={`absolute inset-0 bg-red-200 dark:bg-red-400 w-full h-full object-contain transition-opacity duration-700 ease-in-out ${
          index === currentIndex ? 'opacity-100 z-10' : 'opacity-0 z-0'
        }`}
      />
    {/each}
  </div>

  <!-- Navigation Buttons -->
  <button
    on:click={prevImage}
    class="absolute top-1/2 left-2 -translate-y-1/2 transition-opacity text-white dark:text-red-400 bg-red-400 dark:bg-white rounded-full p-2 hover:bg-red-600 dark:hover:bg-red-200 z-20"
    aria-label="Previous"
  >
    <CaretLeftSolid class="w-5 h-5" />
  </button>

  <button
    on:click={nextImage}
    class="absolute top-1/2 right-2 -translate-y-1/2 transition-opacity text-white dark:text-red-400 bg-red-400 dark:bg-white rounded-full p-2 hover:bg-red-600 dark:hover:bg-red-200 z-20"
    aria-label="Next"
  >
    <CaretRightSolid class="w-5 h-5" />
  </button>
</div>