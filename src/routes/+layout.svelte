<script lang="ts">
	import '../style/app.css';
	import imgKoranda from '$lib/imgs/koranda-wide.png';
	import imgPrinceton from '$lib/imgs/princeton-logo-white.svg';
	import imgCampusRec from '$lib/imgs/campusrec-logo.png';

	let { children } = $props();
</script>

<svelte:head>
	<title>Princeton Rugby</title>
</svelte:head>

<div class="min-h-screen">
	{@render children()}
</div>

<div class="footer w-full bg-black text-white">
	<div class="w-full">
		<img src={imgKoranda} alt="Koranda Cup" />
	</div>
	<div class="grid grid-cols-2 md:grid-cols-5 gap-2 px-10 md:px-20 py-6 text-2xl">
		<div class="col-span-2 flex items-center justify-center font-mono py-2 md:py-0 text-8xl font-bold italic">
			@PURFC
		</div>
		<div class="md:ml-10 flex flex-col text-xl">
			<div class="my-3 font-bold">Quick Links</div>
			<div>
				<a class="hover:text-pton transition-colors" href="https://princetonrugby.com">Home</a>
			</div>
			<div><a class="hover:text-pton transition-colors" href="/">Men</a></div>
			<div>
				<a class="hover:text-pton transition-colors" href="https://princetonrugby.com">Women</a>
			</div>
		</div>
		<div class="md:ml-10 flex flex-col text-xl">
			<div class="my-3 font-bold">Men</div>
			<div><a class="hover:text-pton transition-colors" href="/join">Join</a></div>
			<div><a class="hover:text-pton transition-colors" href="/schedule">Schedule</a></div>
			<div><a class="hover:text-pton transition-colors" href="/contact">Contact</a></div>
		</div>
		<div class="md:ml-10 flex flex-col text-xl">
			<div class="my-3 font-bold">Women</div>
			<div>
				<a
					class="hover:text-pton transition-colors"
					href="https://goprincetontigers.com/sports/womens-rugby/roster">Roster</a
				>
			</div>
			<div>
				<a
					class="hover:text-pton transition-colors"
					href="https://goprincetontigers.com/sports/womens-rugby/schedule">Schedule</a
				>
			</div>
			<div>
				<a class="hover:text-pton transition-colors" href="https://www.facebook.com/puwrfc"
					>Facebook</a
				>
			</div>
			<div>
				<a class="hover:text-pton transition-colors" href="https://instagram.com/princetonwrugby"
					>Instagram</a
				>
			</div>
		</div>
	</div>
	<div class="princeton flex flex-col justify-center md:grid grid-cols-3 gap-4 px-10 py-6">
		<a href="https://www.princeton.edu/">
			<img class="md:w-50" src={imgPrinceton} alt="Princeton University" />
		</a>
		<a class="flex items-center justify-center" href="https://campusrec.princeton.edu">
			<img class="md:w-70" src={imgCampusRec} alt="Princeton University" />
		</a>
		<div class="flex flex-col items-end justify-center text-sm">
			<span>© 2025 The Trustees of Princeton University</span>
			<span>Princeton, NJ 08544</span>
		</div>
	</div>
</div>
