<script lang="ts">
    import IconList from './ui/IconList.svelte';
    import Input from './ui/Input.svelte';
    import {
        doc,
        setDoc
    } from 'firebase/firestore';
    import {
        waitlistCollection
    } from '$lib/utils/firebase';

    let name = '';
    let email = '';

    const nameRegex = /^[A-Za-z\s.'-]+$/;
    const emailRegex = /^[a-zA-Z0-9.!#$%&'*+\/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$/;
</script>

<section class="mt-20 flex min-h-screen max-w-full flex-col gap-10 overflow-hidden px-4 md:px-0" id="faq">

    <div class="flex flex-col items-center gap-8">
        <h1 class="text-left text-3xl font-semibold text-slate-200 sm:text-5xl">
            FAQ
        </h1>

        <h5 class="text-left text-xl font-semibold text-slate-200 sm:text-xl">
            Does SingularityLabs monetise our data ?
        </h5>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            No we don't, our only montization is subscription fees of out paid users
        </p>
    </div>
</section>