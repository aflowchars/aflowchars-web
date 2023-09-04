<!-- Header -->
<header class="relative py-6">
	<div
		class="relative aspect-video w-full overflow-hidden border-stone-950 before:absolute before:z-10 before:h-full before:w-full before:bg-gradient-to-t before:from-stone-950/50 before:via-stone-700/25 before:to-stone-50/0"
	>
		<img
			class="h-full w-full scale-100 transform object-cover object-left-top transition-transform duration-300 ease-linear group-hover:scale-[1.0125]"
			src="https://images.unsplash.com/photo-1516542076529-1ea3854896f2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1471&q=80"
			alt="Foto"
		/>

		<div class="absolute bottom-12 left-12 z-20 text-white">
			<h1 class="mb-3 w-full max-w-3xl text-4xl font-medium">
				Cara Menangkap Event Keyboard di Svelte
			</h1>
			<div>
				Ditulis oleh
				<a href="/about" class="font-medium hover:underline">
					Afochar Syabnirusmanto
				</a>
			</div>
		</div>
	</div>
</header>

<!-- Content -->
<section class="container mx-auto max-w-screen-md space-y-6 py-8 text-lg">
	<figure class="relative border border-stone-950 p-4 pl-6 text-base">
		<span class="absolute left-0 top-0 h-full w-1.5 bg-stone-950"></span>

		<p class="mb-2">
			KeyboardEvent objects describe a user interaction with the keyboard; each
			event describes a single interaction between the user and a key (or
			combination of a key with modifier keys) on the keyboard. The event type
			(keydown, keypress, or keyup) identifies what kind of keyboard activity
			occurred.
		</p>

		<a
			class="group flex items-center gap-1 font-medium underline"
			href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent"
		>
			KeyboardEvents - Dev Mozilla

			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				class="h-5 w-5 rotate-45 transform opacity-0 transition-opacity duration-300 ease-in group-hover:opacity-100"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M12 19.5v-15m0 0l-6.75 6.75M12 4.5l6.75 6.75"
				/>
			</svg>
		</a>
	</figure>

	<div class="space-y-6 text-justify">
		<p class="first-letter:text-3xl first-letter:font-medium">
			Seringkali ketika kita menggunakan Chrome, Word, dll kita biasa disajikan
			dengan kombinasi ketikan keyboard yang memudahkan interaksi kita ketika
			mengerjakan sesuatu dengan aplikasi tersebut. Ctrl + S untuk Save, Ctrl +
			Z untuk Undo di Word. Ctrl + T di Chrome untuk membuka Tab Baru. Hingga
			bermacam kombinasi lainnya..
		</p>

		<p>
			Bermula dari itu, maka rasa penasaran saya muncul.. Lalu bagaimana cara
			kita untuk bisa membuat seperti itu? Hal pertama yang muncul dalam membuat
			website ini adalah ketika membuat Navbar. Ya, navigasi di atas merupakan
			ajang pertama eksperimen saya untuk mencoba KeyboardEvent.
		</p>

		<p>
			Jika temen-temen mencoba click Menu di Navbar maka akan terlihat
			list-menu. Ketika list menu aktif, bisa dicoba untuk menekan tombol Esc.
			Maka, list menu akan tertutup tanpa harus mengarahkan mouse ke button
			tutup. Ini tentu memudahkan navigasi pengguna yang sudah terbiasa dengan
			penggunaan keyboard.
		</p>

		<p>
			Karena website ini dibangun dengan SvelteKit. Maka mari kita coba buat
			dengan Svelte. Kenapa tidak menggunakan React atau Vue? Karena lebih mudah
			saja bagi saya. Hehehehe
		</p>
	</div>

	<figure class="relative border border-stone-950 p-4 pl-6 text-base">
		<span class="absolute left-0 top-0 h-full w-1.5 bg-stone-950"></span>

		<p class="mb-2">
			Just as you can add event listeners to any DOM element, you can add event
			listeners to the window object with {'<svelte:window>'}.
		</p>

		<a
			class="group flex items-center gap-1 font-medium underline"
			href="https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent"
		>
			Svelte Window - Tutorial Svelte.dev

			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				class="h-5 w-5 rotate-45 transform opacity-0 transition-opacity duration-300 ease-in group-hover:opacity-100"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M12 19.5v-15m0 0l-6.75 6.75M12 4.5l6.75 6.75"
				/>
			</svg>
		</a>
	</figure>

	<p>
		Langsung saja pertama siapkan +page.svelte baru.. Kemudian buatlah sebuah
		navbar dan navbar list menu. Disini saya menggunakan Tailwind CSS sebagai
		styling
	</p>

	<img src="/article-1.png" alt="Articles" />

	<p>
		Setelah membuat HTML Navbar kita bisa membuat script untuk 'toggling' menu
		dari navbar. Disini kita akan menggunakan tag button Menu sebagai toggler.
		Selanjutnya tinggal membuat logika yang berjalan bagi navbar. <br /> <br />
		Pertama-tama buat sebuah variabel bernama
		<span class="font-medium">let show_menu.</span>
		Variabel ini bertipe boolean dan berfungsi untuk membuka atau menutup navbar.

		<br /><br />

		Lalu, buat sebuah function yang menangkap event KeyDown yang sudah kita
		definisikan sebelumnya dengan special tag dari svelte yakni
		<span class="font-medium">{'<svelte:window />'}</span>
	</p>

	<img src="/article-2.png" alt="Articles" />
</section>
