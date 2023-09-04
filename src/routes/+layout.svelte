<script>
	// --------------------------------------------------------------------------------------//
	import '../app.css';
	import { onMount } from 'svelte';
	import { fly } from 'svelte/transition';

	// --------------------------------------------------------------------------------------//
	import { XMarkIcon } from '$lib/icons';
	import { AflowcharsLogo } from '$lib';
	// --------------------------------------------------------------------------------------//
	let show_menu = false;

	function handleMenuOpen() {
		show_menu = !show_menu;

		if (show_menu) {
			window.document.addEventListener('click', handleMenuClose);
		}
	}
	function handleMenuClose() {
		show_menu = false;

		document.body.removeEventListener('click', handleMenuClose);
	}
	// --------------------------------------------------------------------------------------//
	let show_contact = false;

	function handleContactOpen() {
		show_contact = !show_contact;

		if (show_contact) {
			window.document.addEventListener('click', handleContactClose);
		}
	}
	function handleContactClose() {
		show_contact = false;

		document.body.removeEventListener('click', handleContactClose);
	}
	// --------------------------------------------------------------------------------------//
	/**
	 * @param {KeyboardEvent} event
	 */
	function closeNavbarEsc(event) {
		if (show_contact) {
			if (event.key === 'Escape') {
				show_contact = false;
			}
		}

		if (show_menu) {
			if (event.key === 'Escape') {
				show_menu = false;
			}
		}
	}
	// --------------------------------------------------------------------------------------//
	let show_caution = false;

	onMount(() => {
		setTimeout(() => {
			show_caution = true;
		}, 3000);

		setTimeout(() => {
			show_caution = false;
		}, 10000);
	});
	// --------------------------------------------------------------------------------------//
</script>

<svelte:window on:keydown={closeNavbarEsc} />

<svelte:head>
	<title>Aflowchars</title>
	<link rel="icon" href="/favicon.svg" />
</svelte:head>

<!-- Navbar -->
<nav
	class="navbar fixed inset-0 z-50 flex h-20 w-full items-center justify-center bg-stone-50"
>
	<div
		class="container mx-auto flex h-full max-w-screen-lg items-center justify-between border-b border-stone-950 px-12"
	>
		<!-- Menu -->
		<button
			on:click|stopPropagation={handleMenuOpen}
			class="w-32 text-left font-medium outline-0 hover:underline"
		>
			{show_menu ? 'Tutup' : 'Menu'}
		</button>

		<!-- Logo -->
		<a data-sveltekit-preload-data href="/">
			<AflowcharsLogo class="h-10 stroke-2 text-stone-950" />
		</a>

		<!-- Contact -->
		<button
			on:click|stopPropagation={handleContactOpen}
			class="w-32 text-right font-medium outline-0 hover:underline"
		>
			{show_contact ? 'Tutup' : 'Contact'}
		</button>
	</div>
</nav>

{#if show_menu}
	<nav
		transition:fly={{ y: 16, duration: 300 }}
		class="fixed inset-0 top-20 z-50 flex h-16 flex-row items-center gap-4 bg-stone-50"
	>
		<div
			class="container mx-auto flex h-full max-w-screen-lg items-center justify-between border-b border-stone-950 px-24"
		>
			<a class="px-6 py-3 font-medium hover:underline" href="/">Home</a>
			<a class="px-6 py-3 font-medium hover:underline" href="/">Tulisan</a>
			<a class="px-6 py-3 font-medium hover:underline" href="/">Project</a>
			<a class="px-6 py-3 font-medium hover:underline" href="/">Tentang</a>
		</div>
	</nav>
{/if}

{#if show_contact}
	<nav
		transition:fly={{ y: 16, duration: 300 }}
		class="fixed inset-0 top-20 z-50 flex h-16 flex-row items-center gap-4 bg-stone-50"
	>
		<div
			class="container mx-auto flex h-full max-w-screen-lg items-center justify-between border-b border-stone-950 px-24"
		>
			<a class="px-6 py-3 font-medium hover:underline" href="/">Instagram</a>
			<a class="px-6 py-3 font-medium hover:underline" href="/">Youtube</a>
			<a class="px-6 py-3 font-medium hover:underline" href="/">Dribbble</a>
			<a class="px-6 py-3 font-medium hover:underline" href="/">Github</a>
		</div>
	</nav>
{/if}

<!-- Main -->
<main class="container relative mx-auto mt-20 max-w-screen-lg">
	<slot />
</main>

<footer class="container mx-auto max-w-screen-lg py-6">
	<div
		class="flex w-full items-center justify-between border-y border-stone-950 px-12 py-4"
	>
		<a data-sveltekit-preload-data href="/">
			<AflowcharsLogo
				class="h-8 w-8 flex-shrink-0 stroke-[1.5px] text-stone-950"
			/>
		</a>

		<h5 class="text-base font-normal">&copy; Copywrong 2023</h5>
	</div>
</footer>

{#if show_caution}
	<figure
		transition:fly={{ y: 16, duration: 300 }}
		class="fixed bottom-8 right-8 z-50 w-64 border border-stone-950"
	>
		<nav
			class="flex items-center justify-between border-b border-stone-950 px-4 py-2"
		>
			<h5 class="text-sm">Information</h5>

			<button on:click={() => (show_caution = false)}>
				<XMarkIcon class="h-4 w-4 stroke-2 text-stone-950" />
			</button>
		</nav>

		<div class="px-4 py-6">Website ini sedang dibangun. Harap tunggu..</div>

		<button
			on:click={() => (show_caution = false)}
			class="w-full bg-stone-950 py-1.5 text-center text-sm text-white hover:underline"
		>
			Oke
		</button>
	</figure>
{/if}
