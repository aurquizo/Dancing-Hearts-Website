<script lang="ts">
	import { DiscordSolid, YoutubeSolid, XSolid } from 'flowbite-svelte-icons';

	let members = [
		{
			href: '/',
			src: '/images/isa.jpeg',
			alt: 'Isabelle Urquizo',
			name: 'Isabelle Urquizo',
			jobTitle: 'Founder',
			description: 'ygygygyg'
		},
		{
			href: '/',
			src: '/images/diana.jpeg',
			alt: 'Diana Duran',
			name: 'Diana Duran',
			jobTitle: 'Co-Founder',
			description: 'Jese drives the technical strategy of the flowbite platform and brand.'
		},
		{
			href: '/',
			src: '/images/nancy.jpeg',
			alt: 'Nancy Misioka',
			name: 'Nancy Misioka',
			jobTitle: 'Co-Founder',
			description: 'Michael drives the technical strategy of the flowbite platform and brand.'
		}
	];
</script>

<section class="py-12 bg-white dark:bg-gray-900">
	<div class="max-w-screen-xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="text-center mb-12">
			<h2 class="text-4xl font-extrabold tracking-tight text-gray-900 dark:text-white">Our Team</h2>
			<p class="mt-4 text-lg text-gray-500 dark:text-gray-400">
				Explore the whole collection of open-source web components and elements built with the utility classes from Tailwind
			</p>
		</div>

		<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-2 lg:grid-cols-3 gap-8">
			{#each members as member}
				<div class="bg-white dark:bg-gray-800 rounded-lg shadow p-6 text-center">
					<a href={member.href}>
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
						<a href="/" aria-label="Facebook"><DiscordSolid class="w-5 h-5 hover:text-blue-600" /></a>
						<a href="/" aria-label="GitHub"><YoutubeSolid class="w-5 h-5 hover:text-gray-800 dark:hover:text-white" /></a>
						<a href="/" aria-label="Twitter"><XSolid class="w-5 h-5 hover:text-blue-400" /></a>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
