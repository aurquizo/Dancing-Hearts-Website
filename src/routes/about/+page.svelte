<script lang="ts">
	import { DiscordSolid, YoutubeSolid, XSolid, InstagramSolid } from 'flowbite-svelte-icons';
	import Icon from '@iconify/svelte';

	let members = [
		{
			src: '/images/isa.jpeg',
			alt: 'Isabelle Urquizo',
			name: 'Isabelle Urquizo',
			jobTitle: 'Founder',
			description: 'Main Choreographer for Dancing Hearts',
			links: {
				instagram: 'https://www.instagram.com/isabelleurquizo?utm_source=ig_web_button_share_sheet&igsh=ZDNlZDc0MzIxNw==',
				youtube: 'https://youtube.com/@isabelleurquizo?si=y4m0sgiPgdM50SC5',
				tiktok: 'https://www.tiktok.com/@isabelleurquizo?is_from_webapp=1&sender_device=pc'
			}
		},
		{
			src: '/images/diana.jpeg',
			alt: 'Diana Duran',
			name: 'Diana Duran',
			jobTitle: 'Co-Founder',
			description: 'Manager',
			links: {
				instagram: 'https://www.instagram.com/diana_vett/?utm_source=ig_web_button_share_sheet'
			}
		},
		{
			src: '/images/nancy.jpeg',
			alt: 'Nancy Misioka',
			name: 'Nancy Misioka',
			jobTitle: 'Co-Founder',
			description: 'Assistant Choregrapher',
			links: {
				instagram: 'https://www.instagram.com/tuamoni22?utm_source=ig_web_button_share_sheet&igsh=ZDNlZDc0MzIxNw==',
				snapchat: 'https://snapchat.com/t/uCkbCHi4'
			}
		}
	];
</script>

<section class="py-12 bg-white dark:bg-red-400 overflow-hidden">
	<div class="max-w-screen-xl mx-auto px-4 sm:px-6 lg:px-8 pb-20">
		<div class="text-center mb-10 sm:mb-12">
			<h2 class="text-4xl font-extrabold tracking-tight text-gray-900 dark:text-white">Our Team</h2>
			<p class="mt-4 text-lg text-gray-500 dark:text-white">
				Hello! We are a dance company located in El Paso, Texas who love to teach and inspire students to use their artistic creations to the full extent!
			</p>
		</div>

		<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 md:gap-8">
			{#each members as member}
			<div class="bg-white dark:bg-gray-800 rounded-lg shadow p-6 text-center w-full max-w-sm mx-auto">
					<!-- svelte-ignore a11y_missing_attribute -->
					<a>
						<img
							src={member.src}
							alt={member.alt}
							class="w-24 h-24 mx-auto mb-4 rounded-full object-cover"
						/>
					</a>
					<h3 class="text-xl font-semibold text-gray-900 dark:text-white">{member.name}</h3>
					<p class="text-sm text-gray-500 dark:text-gray-400">{member.jobTitle}</p>
					<p class="mt-3 text-gray-600 dark:text-gray-400 text-sm">{member.description}</p>
					<div class="mt-4 flex justify-center space-x-4 text-gray-500 dark:text-gray-400">
						{#if member.links.instagram}
						  <a href={member.links.instagram} target="_blank" aria-label="Instagram">
							<InstagramSolid class="w-5 h-5 hover:text-pink-600" />
						  </a>
						{/if}
						{#if member.links.youtube}
						  <a href={member.links.youtube} target="_blank" aria-label="YouTube">
							<YoutubeSolid class="w-5 h-5 hover:text-red-600" />
						  </a>
						{/if}
						{#if member.links.tiktok}
						  <a href={member.links.tiktok} target="_blank" aria-label="TikTok">
							<Icon icon="simple-icons:tiktok" class="w-5 h-5 hover:text-purple-800" />
						  </a>
						{/if}
						{#if member.links.snapchat}
						  <a href={member.links.snapchat} target="_blank" aria-label="Snapchat">
							<Icon icon="simple-icons:snapchat" class="w-5 h-5 hover:text-yellow-400" />
						  </a>
						{/if}
					  </div>
				</div>
			{/each}
		</div>
	</div>
</section>
