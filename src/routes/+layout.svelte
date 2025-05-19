<script lang="ts">
	import '../style/app.css';
	import imgKoranda from '$lib/imgs/koranda-wide.png';
	import imgPrinceton from '$lib/imgs/princeton-logo-white.svg';
	import imgCampusRec from '$lib/imgs/campusrec-logo.png';
	import { Icon } from 'svelte-awesome';
	import facebook from 'svelte-awesome/icons/facebookSquare';
	import instagram from 'svelte-awesome/icons/instagram';

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
	<div class="grid grid-cols-4 gap-2 px-10 py-6 text-2xl lg:grid-cols-5 md:px-20">
		<div
			class="lg:col-span-2 flex items-center justify-center py-2 font-mono text-6xl lg:text-8xl font-bold italic md:py-0"
		>
			@PURFC
		</div>
		<div class="flex flex-col text-xl md:ml-10">
			<div class="my-3 font-bold">Quick Links</div>
			<div>
				<a class="hover:text-pton transition-colors" href="https://princetonrugby.com">Home</a>
			</div>
			<div><a class="hover:text-pton transition-colors" href="/">Men</a></div>
			<div>
				<a class="hover:text-pton transition-colors" href="https://princetonrugby.com">Women</a>
			</div>
		</div>
		<div class="flex flex-col text-xl md:ml-10">
			<div class="my-3 font-bold">Men</div>
			<div><a class="hover:text-pton transition-colors" href="/join">Join</a></div>
			<div><a class="hover:text-pton transition-colors" href="/schedule">Schedule</a></div>
			<div><a class="hover:text-pton transition-colors" href="/contact">Contact</a></div>
			<div>
				<a
					class="hover:text-pton flex items-center transition-colors"
					href="https://www.facebook.com/princetonrugby"
				>
					<div class="icon flex h-5 w-6 items-center">
						<Icon scale={1.3} data={facebook} />
					</div>
					Facebook
				</a>
			</div>
			<div>
				<a
					class="hover:text-pton flex items-center transition-colors"
					href="https://www.instagram.com/princetonmrugby"
				>
					<div class="icon flex h-5 w-6 items-center">
						<Icon scale={1.3} data={instagram} />
					</div>
					Instagram
				</a>
			</div>
		</div>
		<div class="flex flex-col text-xl md:ml-10">
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
					href="https://goprincetontigers.com/sports/womens-rugby/schedule"
				>
					Schedule
				</a>
			</div>
			<div>
				<a
					class="hover:text-pton flex items-center transition-colors"
					href="https://www.facebook.com/puwrfc"
				>
					<div class="icon flex h-5 w-6 items-center">
						<Icon scale={1.3} data={facebook} />
					</div>
					Facebook
				</a>
			</div>
			<div>
				<a
					class="hover:text-pton flex items-center transition-colors"
					href="https://instagram.com/princetonwrugby"
				>
					<div class="icon flex h-5 w-6 items-center">
						<Icon scale={1.3} data={instagram} />
					</div>
					Instagram
				</a>
			</div>
		</div>
	</div>
	<div class="princeton grid-cols-3 flex flex-col justify-center gap-4 px-10 py-6 md:grid">
		<a href="https://www.princeton.edu/">
			<img class="md:w-50" src={imgPrinceton} alt="Princeton University" />
		</a>
		<a class="flex items-center justify-center" href="https://campusrec.princeton.edu">
			<img class="md:w-70" src={imgCampusRec} alt="Princeton University" />
		</a>
		<div class="flex flex-col items-end justify-center text-right text-xs lg:text-sm">
			<span>© 2025 The Trustees of Princeton University</span>
			<span>Princeton, NJ 08544</span>
		</div>
	</div>
</div>
