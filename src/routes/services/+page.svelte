<script>
  import { Heart, Sparkles, Crown, User, Presentation, CalendarCheck } from 'lucide-svelte';
</script>


<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-row-3 cols-2 gap-30 p-16">
    <div class="bg-white dark:bg-red-400 rounded-xl shadow-lg p-6 text-center">
      <Heart class="mx-auto h-12 w-12 text-red-500 dark:text-red-800 mb-4" />
      <h3 class="text-xl dark:text-white font-bold mb-2">Weddings</h3>
      <p class="text-gray-600 dark:text-white">Elegant, unforgettable performances for your big day!</p>
    </div>

    <div class="bg-white dark:bg-red-400 rounded-xl shadow-lg p-6 text-center">
      <User class="mx-auto h-12 w-12 text-indigo-500 dark:text-indigo-600 mb-4" />
      <h3 class="text-xl dark:text-white font-bold mb-2">Private Lessons</h3>
      <p class="text-gray-600 dark:text-white">One-on-one sessions tailored to your style and goals!</p>
    </div>
  
    <div class="bg-white dark:bg-red-400 rounded-xl shadow-lg p-6 text-center">
      <Crown class="mx-auto h-12 w-12 text-yellow-400 dark:text-yellow-800 mb-4" />
      <h3 class="text-xl dark:text-white font-bold mb-2">Quinceañeras</h3>
      <p class="text-gray-600 dark:text-white">Celebrate your 15 with a powerful and fun dance!</p>
    </div>
  
    <div class="bg-white dark:bg-red-400 rounded-xl shadow-lg p-6 text-center">
      <Presentation class="mx-auto h-12 w-12 text-violet-500 dark:text-violet-800 mb-4" />
      <h3 class="text-xl dark:text-white font-bold mb-2">Workshops</h3>
      <p class="text-gray-600 dark:text-white">Learn a full dance routine in a fun, supportive workshop setting!</p>
    </div>

    <div class="bg-white dark:bg-red-400 rounded-xl shadow-lg p-6 text-center">
      <Sparkles class="mx-auto h-12 w-12 text-pink-500 dark:text-pink-800 mb-4" />
      <h3 class="text-xl dark:text-white font-bold mb-2">Sweet 16s</h3>
      <p class="text-gray-600 dark:text-white">Make your Sweet 16 shine with a custom dance routine!</p>
    </div>
  
    <div class="bg-white dark:bg-red-400 rounded-xl shadow-lg p-6 text-center">
      <CalendarCheck class="mx-auto h-12 w-12 text-green-500 dark:text-green-800 mb-4" />
      <h3 class="text-xl dark:text-white font-bold mb-2">Events</h3>
      <p class="text-gray-600 dark:text-white">Book a live dance instructor to energize your party, school, or corporate event!</p>
    </div>
</div>
  