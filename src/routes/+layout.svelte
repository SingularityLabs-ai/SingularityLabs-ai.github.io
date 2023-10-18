<script lang="ts">
	export const prerender = true;

	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import './styles.css';
	import logo from '$lib/images/logo_small.png';
	import { onMount } from 'svelte';

	function handleAnchorClick(event: any) {
		event.preventDefault();
		const link = event.currentTarget;
		const anchorId = new URL(link.href).hash.replace('#', '');
		const anchor = document.getElementById(anchorId);
		if (!anchor) return;
		window.scrollTo({
			top: anchor.offsetTop - 100,
			behavior: 'smooth'
		});
	}

	let animate = false;
	onMount(() => {
		animate = true;
		const anchors = document.querySelectorAll('a[href^="#"]');
		anchors.forEach((anchor) => {
			anchor.addEventListener('click', handleAnchorClick);
		});
	});
</script>

{#if animate}
	<div class="min-h-screen w-full bg-slate-900">
		<Header />

		<main>
			<slot />
		</main>

		<Footer />
	</div>
{/if}

<style>
	a {
		@apply transition-all duration-500;
	}
	a:hover {
		@apply text-slate-500;
	}
</style>
