<script lang="ts">
	import logo from '$lib/images/logo_small.png';
	import Icon from '@iconify/svelte';
</script>

<footer class="mt-20 flex min-h-fit flex-col bg-slate-800 px-5 pb-4 pt-10 md:px-20">
	<div class="flex flex-col gap-5 md:flex-row md:gap-40">
		<div class="flex h-10 flex-row items-center justify-center gap-2">
			<img src={logo} alt="" />
			<h5 class="text-xl font-semibold text-slate-100"><a href="/">SingularityLabs</a></h5>
		</div>

		<div class="flex flex-col gap-4 p-4 text-slate-300">
			<b>Links</b>
			<div class="flex flex-col gap-2 text-sm">
				<a href="https://github.com/SingularityLabs-ai" target="_blank" rel="noreferrer">GitHub Open Source</a>
				<a href="https://github.com/SingularityLabs-ai/singularitylabs-ai/discussions/categories/ideas" target="_blank">I have an idea</a>
			</div>
			<hr class="mt-4 border-slate-700" />
			<b>Legal</b>
			<div class="flex flex-col gap-2 text-sm">
				<a href="/privacypolicy">Privacy Policy</a>
				<a href="">Terms of Service</a>
			</div>
		</div>

		<div class="flex flex-col gap-4 break-all p-4 text-slate-300">
			<b>Support</b>
			<div class="flex flex-col gap-2 text-sm">
				<a href="/#faq" rel="noreferrer">FAQ</a>
				<a href="mailto:labssingularity@gmail.com">Email: <span class="text-slate-400">labssingularity@gmail.com</span></a>
				<a href="https://github.com/orgs/singularitylabs-ai/discussions" target="_blank" rel="noreferrer">GitHub Discussion</a>
				<a href="https://discord.gg/jc4xtF58Ve" target="_blank" rel="noreferrer">Discord</a>
			</div>
			<hr class="mt-4 border-slate-700" />
			<b>Social</b>
			<div class="flex flex-col gap-2 text-sm">
				<a href="https://twitter.com/labssingularity" target="_blank" rel="noreferrer">Twitter</a>
				<a href="https://instagram.com/singuaritylabs" target="_blank" rel="noreferrer">Instagram</a>
				<a href="https://facebook.com/profile.php?id=100094682281956" target="_blank" rel="noreferrer">Facebook</a>
			</div>
		</div>
	</div>

	<hr class="mt-4 border-slate-700" />

	<div class="mt-3 flex flex-row items-center justify-center text-sm text-slate-400">
		Copyright &copy; {new Date().getFullYear()}&nbsp;
		<a href="/">SingularityLabs</a>
	</div>

</footer>


<style>
	a {
		@apply transition-all duration-500;
	}
	a:hover {
		@apply text-slate-400;
	}
</style>
