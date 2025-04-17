<script>
    import { InstagramSolid, YoutubeSolid, FacebookSolid } from 'flowbite-svelte-icons';
    import Icon from '@iconify/svelte';
</script>

<div class="min-h-screen px-4 py-12 bg-white dark:bg-gray-900">
    <!-- Socials Section -->
    <div class="max-w-5xl mx-auto mb-16">
        <h1 class="text-3xl font-bold text-center text-gray-800 dark:text-white mb-8">
        Follow Us On Our Socials
        </h1>

        <div class="grid grid-cols-2 md:grid-cols-4 gap-6 justify-items-center">
        <!-- Instagram -->
        <a
            href="https://www.instagram.com/dancingheartsdco?utm_source=ig_web_button_share_sheet&igsh=ZDNlZDc0MzIxNw=="
            target="_blank"
            rel="noopener noreferrer"
            class="flex flex-col items-center p-6 bg-pink-100 dark:bg-pink-900 rounded-2xl shadow hover:scale-105 transition"
        >
            <InstagramSolid class="w-8 h-8 text-pink-500 dark:text-white mb-2" />
            <span class="text-sm text-gray-700 dark:text-white font-medium">Instagram</span>
        </a>

        <!-- YouTube -->
        <a
            href="https://www.youtube.com/@dancingheartsdco"
            target="_blank"
            rel="noopener noreferrer"
            class="flex flex-col items-center p-6 bg-red-100 dark:bg-red-900 rounded-2xl shadow hover:scale-105 transition"
        >
            <YoutubeSolid class="w-8 h-8 text-red-600 dark:text-white mb-2" />
            <span class="text-sm text-gray-700 dark:text-white font-medium">YouTube</span>
        </a>

        <!-- Facebook -->
        <a
            href="https://www.facebook.com/share/15QcrZnjjv/?mibextid=wwXIfr"
            target="_blank"
            rel="noopener noreferrer"
            class="flex flex-col items-center p-6 bg-blue-100 dark:bg-blue-900 rounded-2xl shadow hover:scale-105 transition"
        >
            <FacebookSolid class="w-8 h-8 text-blue-600 dark:text-white mb-2" />
            <span class="text-sm text-gray-700 dark:text-white font-medium">Facebook</span>
        </a>

        <!-- TikTok -->
        <a
            href="https://www.tiktok.com/@dancingheartsdco?is_from_webapp=1&sender_device=pcß"
            target="_blank"
            rel="noopener noreferrer"
            class="flex flex-col items-center p-6 bg-gray-200 dark:bg-gray-800 rounded-2xl shadow hover:scale-105 transition"
        >
            <Icon icon="simple-icons:tiktok" class="w-8 h-8 text-black dark:text-white mb-2" />
            <span class="text-sm text-gray-700 dark:text-white font-medium">TikTok</span>
        </a>
        </div>
    </div>

    <!-- Message Section Placeholder -->
    <div class="max-w-3xl mx-auto text-center">
        <h2 class="text-2xl font-semibold text-gray-800 dark:text-white mb-4">
        Or Send Us a Message
        </h2>
        <!-- Drop your contact form or input grid here -->
        <p class="text-gray-600 dark:text-gray-400">
        (dgfgfgddf)
        </p>
    </div>
</div>
