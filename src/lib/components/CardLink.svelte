<script lang="ts">
	const { imgSrc, href, black = false, children } = $props();
</script>

<a {href} class="m-1">
	<div
		style="--img: url({imgSrc})"
		class="group relative flex w-45 h-45 md:h-120 md:w-72 items-end overflow-hidden rounded-lg p-2 transition-all duration-300 ease-in-out"
	>
		<div
			class="absolute inset-0 bg-[image:var(--img)] bg-cover bg-center bg-no-repeat brightness-90 transition-all group-hover:scale-105"
		></div>
		<div
			class="absolute opacity-20 from-black group-hover:from-pton group-hover:opacity-30 transition-all inset-0 z-30 rounded-lg bg-gradient-to-tr to-transparent"
		></div>
		<div class="z-40 font-mono font-bold text-white uppercase italic">
			{@render children()}
		</div>
	</div>
</a>
