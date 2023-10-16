<script>
	import IconList from './ui/IconList.svelte';
</script>

<div
	class="relative mt-40 flex min-h-screen w-full flex-col-reverse overflow-hidden px-4 md:px-24 lg:flex-row"
	id="desktop"
>
	<div class="flex flex-col gap-8 pb-20 md:py-20">
		<h3 class="text-4xl font-semibold leading-snug text-slate-300">
			Multiple platforms supported. <br /><span class="text-slate-50">Choose your favourite one!</span>
		</h3>
		<p class="max-w-lg text-xl font-light text-slate-300">
			With state of the art AI, SingularityLabs aims to maximise your productivity while accessing the web.
			Crisp and sharp!
		</p>

		<div class="flex flex-col gap-4">
			<IconList icon="ph:wifi-slash" text="No internet required" />
			<IconList icon="ph:list-checks" text="5+ Modes" />
			<IconList icon="ph:paint-brush" text="Fully Customizable" />
			<IconList icon="ph:leaf" text="Free and Open Source" />
		</div>
	</div>

	<div id="image-container" class="max-h-96 max-w-2xl -right-1/4 left-1/2 lg:absolute">
		<img src="/singularitylabs-desktop.png" alt="SingularityLabs Desktop Screenshot" class="lg:ml-16" />
	</div>
</div>
