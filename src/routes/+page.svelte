<header
	class="flex items-center justify-center border-b border-stone-950 py-20"
>
	<figure class="flex w-64 flex-col items-center border border-stone-950">
		<nav
			class="flex h-8 w-full items-center justify-between border-b border-stone-950 px-5 text-stone-950"
		>
			<h5 class="text-sm font-medium">Intro</h5>

			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.65"
				stroke="currentColor"
				class="h-4 w-4"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M12 4.5v15m0 0l6.75-6.75M12 19.5l-6.75-6.75"
				/>
			</svg>
		</nav>

		<div class="flex flex-col items-center py-8 text-center">
			<img
				class="mb-4 h-24 w-24 rounded-full"
				src="/profile.jpg"
				alt="Afochar S"
			/>
			<h1 class="text-lg font-medium">Afochar Syabnirusmanto</h1>
			<p class="-mt-0.5 text-xs">( Frontend developer )</p>
		</div>

		<button
			class="w-full bg-stone-950 py-2 text-center text-sm font-medium text-white hover:underline"
		>
			Selengkapnya
		</button>
	</figure>
</header>

<section class="relative border-b border-stone-950">
	<nav
		class="flex items-center justify-between border-b border-stone-950 px-12 py-3"
	>
		<h3 class="text-lg font-medium">Tulisan</h3>

		<a
			class="hover:underline"
			href="/tulisan/cara-menangkap-keyboardevent-di-svelte"
		>
			Lihat Semua
		</a>
	</nav>

	<div class="grid grid-cols-2 gap-6 px-12 py-6">
		{#each [1, 2, 3, 4] as blog, index}
			<figure
				class="group relative flex border border-stone-950 {index % 2 === 0
					? 'flex-col-reverse'
					: 'flex-col'} items-start gap-0"
			>
				<!-- svelte-ignore a11y-missing-content -->
				<a
					href="/tulisan/cara-menangkap-event-keyboard-di-svelte"
					class="absolute inset-0 z-10 h-full w-full object-cover"
				/>

				<div
					class="aspect-video w-full {index % 2 === 0
						? 'border-t'
						: 'border-b'} overflow-hidden border-stone-950"
				>
					<img
						class="h-full w-full scale-100 transform object-cover transition-transform duration-300 ease-linear group-hover:scale-[1.0125]"
						src="https://images.unsplash.com/photo-1516542076529-1ea3854896f2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1471&q=80"
						alt="Foto"
					/>
				</div>

				<section>
					<div class="space-y-2 p-3 pt-3.5">
						<h5
							class="text-xl font-medium leading-tight group-hover:underline group-hover:underline-offset-4"
						>
							Cara Menangkap Event Keyboard di Svelte
						</h5>

						<p class="line-clamp-2">
							Lorem ipsum dolor, sit amet consectetur adipisicing elit.
							Reiciendis vero, laudantium aspernatur esse aperiam eius placeat
							iusto quis asperiores ut voluptates dignissimos. Laborum
							perspiciatis et illo iste ea quibusdam ex.
						</p>
					</div>

					<div
						class="flex items-center justify-between border-t border-stone-950 px-3 py-2"
					>
						<div class="flex items-center gap-1">
							<svg
								xmlns="http://www.w3.org/2000/svg"
								fill="none"
								viewBox="0 0 24 24"
								stroke-width="1.5"
								stroke="currentColor"
								class="h-5 w-5"
							>
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 012.25-2.25h13.5A2.25 2.25 0 0121 7.5v11.25m-18 0A2.25 2.25 0 005.25 21h13.5A2.25 2.25 0 0021 18.75m-18 0v-7.5A2.25 2.25 0 015.25 9h13.5A2.25 2.25 0 0121 11.25v7.5"
								/>
							</svg>

							<h5>1 jam yang lalu</h5>
						</div>

						<div class="flex items-center gap-1">
							<svg
								xmlns="http://www.w3.org/2000/svg"
								fill="none"
								viewBox="0 0 24 24"
								stroke-width="1.5"
								stroke="currentColor"
								class="h-5 w-5"
							>
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z"
								/>
							</svg>

							<p>5 menit</p>
						</div>
					</div>
				</section>
			</figure>
		{/each}
	</div>
</section>

<section class="relative">
	<nav
		class="flex items-center justify-between border-b border-stone-950 px-12 py-3"
	>
		<h3 class="text-lg font-medium">Projek</h3>

		<a
			class="hover:underline"
			href="/tulisan/cara-menangkap-keyboardevent-di-svelte"
		>
			Lihat Semua
		</a>
	</nav>

	<div class="space-y-0">
		{#each [1, 2, 3, 4, 5] as item}
			<button
				class="group flex h-20 w-full items-center justify-between border-b border-stone-950 px-12 py-6"
			>
				<h5 class="text-3xl">Nijaworks</h5>

				<svg
					xmlns="http://www.w3.org/2000/svg"
					fill="none"
					viewBox="0 0 24 24"
					stroke-width="1"
					stroke="currentColor"
					class="h-8 w-8 transition-transform duration-500 ease-out group-hover:rotate-45"
				>
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"
					/>
				</svg>
			</button>
		{/each}
	</div>
</section>
