<script>
	export let y;

	export let tabs = [
		{ name: 'About me', link: '#about' },
		{ name: 'Projects', link: '#projects' },
		{ name: 'Contact', link: '#contact' }
	];
</script>

<header
	class={'sticky z-[10] top-0 duration-200 px-6 flex items-center justify-between border-b border-solid ' +
		// If top of page, menu background transparent
		(y > 0 ? ' py-4 bg-slate-950 border-b-2 border-violet-950' : ' py-6 bg-transparent border-transparent')}
>
	<h1 class="font-medium">
		<b class="font-bold poppins">Keko</b> <span class="">Williams</span>
	</h1>

	<!-- Nav links -->
	<div class="sm:flex items-center gap-4 hidden">
		{#each tabs as tab, index}
			<a href={tab.link} class="duration-200 hover:text-violet-400" target={index === 2 ? '' : ''}>
				<p>{tab.name}</p>
			</a>
		{/each}

        <!-- Contact button alternative to link -->
		<!-- <button
			class="blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-white text-slate-950"
		>
			<div
				class="absolute top-0 right-full w-full h-full bg-violet-400 opacity-20 group-hover:translate-x-full z-0 duration-200"
			/>
			<h4 class="relative z-9">Get in touch</h4>
		</button> -->
	</div>
</header>
