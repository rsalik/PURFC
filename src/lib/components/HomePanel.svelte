<script lang="ts">
	const { src, alt, right = false, children } = $props()
</script>

<div class={"flex p-3 md:p-5 flex-col " + (!right ? "md:flex-row" : "md:flex-row-reverse")}>
	<div class="md:w-1/2 mb-5 md:mb-0 md:px-5 flex flex-col justify-center">
		<img class="w-full object-cover min-h-2/3 rounded-lg" {src} {alt} />
	</div>
	<div class="md:w-1/2 px-8 flex flex-col justify-center">
		{@render children()}
	</div>
</div>
