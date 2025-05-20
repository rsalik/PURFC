<script lang="ts">
	import { onMount } from 'svelte';

	import HomePanel from '$lib/components/HomePanel.svelte';

	import imgLanding from '$lib/imgs/landing.webp';
	import imgTeam from '$lib/imgs/team-ivys.webp';
	import imgFergus from '$lib/imgs/dangerous.webp';
	import imgTigerPrint from '$lib/imgs/tiger-print.webp';

	import { Icon } from 'svelte-awesome';
	import chevronDown from 'svelte-awesome/icons/chevronDown';
	import CardLink from '$lib/components/CardLink.svelte';

	const topScroll = 0;
	const bottomScroll = 500;

	const border = 25;
	const dimn = 3;

	let img: HTMLImageElement;

	function handleScroll() {
		const scrollRange = bottomScroll - topScroll;
		const scrollTop = window.scrollY - topScroll;
		const scrollPercent = Math.min(Math.max(scrollTop / scrollRange, 0), 1);

		img.style.borderRadius = `${border * scrollPercent}px`;
		img.style.width = `${100 - dimn * 2 * scrollPercent}vw`;
		img.style.height = `${100 - dimn * scrollPercent}vh`;
	}
</script>

<svelte:window onscroll={handleScroll} />

<div class="bg-pton relative flex h-full w-screen flex-col items-center justify-center text-white">
	<div style="--img: url('{imgTigerPrint}')" class="absolute mask-t-from-black/30 mask-t-to-black/10 inset-0 bg-[image:var(--img)]"></div>
	<div class="relative flex h-screen w-screen items-center justify-center">
		<div
			class="title absolute z-10 -mt-10 flex h-full w-full flex-col items-center justify-center px-16 text-center font-serif text-6xl font-bold text-wrap md:mt-0 md:px-5 md:text-[7vw]"
		>
			<span class="font-normal italic md:tracking-wide">Princeton University</span>
			<span class="md:tracking-tight">Rugby Football Club</span>
		</div>
		<div class="absolute right-0 bottom-8 left-0 z-20 flex justify-center opacity-80">
			<Icon scale={3} data={chevronDown} />
		</div>
		<img loading="lazy" class="landing-img" src={imgLanding} alt="Landing" bind:this={img} />
	</div>

	<div class="relative flex justify-center overflow-clip p-2">
		<CardLink imgSrc={imgFergus} href="/join">
			<div class="text-5xl">Join</div>
		</CardLink>
		<CardLink black imgSrc={imgLanding} href="/schedule">
			<div class="text-4xl text-[2.75rem]">Schedule</div>
		</CardLink>
		<CardLink imgSrc={imgTeam} href="/join">
			<div class="text-5xl">Giving</div>
		</CardLink>
		<CardLink black imgSrc={imgLanding} href="/join">
			<div class="text-5xl">Contact</div>
		</CardLink>
	</div>
</div>

<HomePanel src={imgTeam} alt="Team Portrait">
	<div class="font-serif text-4xl font-semibold">New Players</div>
	<br />
	<p class="text-lg">
		We welcome all serious athletes who are looking to play a team-oriented, physical sport. Rugby
		combines many aspects of football, soccer, and basketball. We welcome new players throughout
		both the fall and spring season, and no rugby experience is needed to join. Come out to a
		practice or two to meet the team and give rugby a try. If you do, we know many of you will grow
		to love the sport and find a welcome home at Princeton as members of the university Rugby Club.

		<br />
		<br />

		Prospective players, <a href="/join" class="text-pton underline">click here to join.</a>

		<br />
		<br />

		For other inquiries, <a href="/join" class="text-pton underline">contact us.</a>
	</p>
</HomePanel>

<HomePanel right src={imgFergus} alt="Player running towards the camera">
	<div class="font-serif text-4xl font-semibold">Schedule</div>
	<br />
	<p class="text-lg">
		Men's Rugby has both a fall and spring season. Lorem ipsum dolor, sit amet consectetur
		adipisicing elit. Amet quibusdam explicabo eum nesciunt cumque dolore nobis itaque incidunt eos
		ducimus. Autem est architecto culpa omnis beatae in, error sequi modi
	</p>
</HomePanel>

<style>
	.landing-img {
		width: 100vw;
		height: 100vh;
		object-fit: cover;
		border-radius: 0;

		filter: brightness(0.7);
	}
</style>
