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
            No we don't, our only montization is subscription fees of out paid users. However you must read terms of service of the respective company who owns the models to know if they monetise the data or not
        </p>

        <h5 class="text-left text-xl font-semibold text-slate-200 sm:text-xl">
            Does SingularityLabs use our data to train its models ?
        </h5>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            No we don't. However you must read terms of service of the respective company who owns the models to know if they would use user data to train their future models or not
        </p>

        <h5 class="text-left text-xl font-semibold text-slate-200 sm:text-xl">
            What can I use the bots for?
        </h5>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            You can use the bots for learning, writing help, translation, programming help, summarization, entertainment, or many other things. We encourage you to explore and discover what Poe is most helpful for in your case.
        </p>

        <h5 class="text-left text-xl font-semibold text-slate-200 sm:text-xl">
            What are the differences between the bots?
        </h5>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            Each bo has a distinct personality that you can get to know over time. You can try them all and decide which you like best for yourself.
        </p>


        <h5 class="text-left text-xl font-semibold text-slate-200 sm:text-xl">
            Should I trust what a bot says?
        </h5>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            The bots are usually correct, but may make incorrect statements, so if you are making an important decision based on information from a bot, you will want to verify the information elsewhere. The bots also should not be solely relied upon for medical, legal or investing advice – please consult a professional. And the bots may not have knowledge of current events, so some information may be out of date. We expect all of these issues to improve considerably as AI research continues.
        </p>

        <h5 class="text-left text-xl font-semibold text-slate-200 sm:text-xl">
            Can other people using Poe see my conversations with the bots?
        </h5>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            No. Conversations with bots are private and are not visible to other users of Poe.
        </p>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            If you tap the Share button, you will be prompted to choose any messages you want to share with others, and the messages you select will then be copied to a new share object, which will be visible to whoever you share it with.
        </p>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            If you choose “Share on Poe” as part of the share flow, the messages you have chosen to share will be copied to a post that will be visible to other Poe users.
        </p>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            You can see all of your posts on Poe on your profile, which you can access via the left side menu (accessible from the button in the top left of the screen in the bot conversation view). You can delete any of your posts from the “...” menu, accessible in the top right of the post view.
        </p>

        <h5 class="text-left text-xl font-semibold text-slate-200 sm:text-xl">
            Was the AI used for the bots trained on Quora answers?
        </h5>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            Not currently. If we do this in the future, we will allow Quora writers to opt out if they want. See this blog post for more detail.
        </p>

        <h5 class="text-left text-xl font-semibold text-slate-200 sm:text-xl">
            Who can see what I’ve liked or posts that other Poe users have shared?
        </h5>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-xl">
            Similar to social media platforms, if you like a post from another user on Poe, other users will be able to see that you liked it. And just like “stories” products on other social media platforms, if you are following the creator of a post, they will be able to see that you have viewed it. You can see who you are following by visiting your profile, accessible from the menu on the left.
        </p>
    </div>
</section>