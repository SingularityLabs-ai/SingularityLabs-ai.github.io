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

<section class="mt-20 flex min-h-screen max-w-full flex-col gap-10 overflow-hidden px-4 md:px-0" id="privacypolicy">
    <div class="flex flex-col items-center gap-8">
        <h1 class="text-left text-2xl font-semibold text-slate-200 sm:text-5xl">
            Terms of Service <span class="text-base text-slate-400 sm:text-2xl">(detailed)</span>
        </h1>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            Last updated: Oct 10, 2023
        </p>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            These Terms of Service (Terms) are a contract between you and Singularity Labs Inc, Inc., and its affiliates (collectively, "we" or "us") regarding your use of the SingularityLabs AI Platform service (the "Service"). In these Terms, "you" refers to you as an individual and to the organization you represent. By using the Service, you agree to these Terms of Service.
        </p>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            If you buy a subscription to SingularityLabs AI Platform, the Subscriber Terms will also apply. SingularityLabs AI Platform is part of the "Platform" for the purposes of the Platform Terms of Service. Capitalized terms in these Terms of Service that are not defined have the same meaning as they do in the Platform Terms of Service.
        </p>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            If you live in the United States or Canada, you agree that any disputes between you and Singularity Labs Inc will be resolved through binding, individual arbitration. This means that you give up your right to participate in a class action lawsuit or class-wide arbitration. We explain this process, some exceptions, and how you can opt out of arbitration in Section 10 of the Platform Terms of Service.
        </p>

        <h2 class="text-left text-lg font-semibold text-slate-200 sm:text-4xl">
            A Platform for Open Exploration
        </h2>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            SingularityLabs AI Platform is a platform where you can explore and interact with a variety of bots powered by large language models (LLMs) from third-party developers, including OpenAI and Anthropic. You may also be able to create your own bots powered by these LLMs. You can use bots for a variety of purposes, such as learning, writing, translation, programming help, summarization, and entertainment. Each bot has a description in its profile, including the name of the company, developer, or individual who created it. Usage guidelines for all bots can be found at https://github.com/sylabs/singularity or in your settings. SingularityLabs AI Platform is a platform for accessing third-party bots, but does not provide or take responsibility for the content or services available from these bots.
        </p>
        <h2 class="text-left text-lg font-semibold text-slate-200 sm:text-4xl">
            Age Requirements
        </h2>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            No one under 13 years old is allowed to use SingularityLabs AI Platform. You must be at least the legal age of majority in the jurisdiction where you live. If you are not, your parent or legal guardian must agree to these Terms of Service on your behalf and accept responsibility for your use of the platform. Bots on SingularityLabs AI Platform may produce content that is not suitable for minors. If you are accepting these Terms of Service on behalf of someone else or an organization, you confirm that you have the legal authority to do so.
        </p>

        <h3 class="text-left text-lg font-semibold text-slate-200 sm:text-2xl">
            Your Use
        </h3>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            Do not rely on bots on SingularityLabs AI Platform during emergencies. Bots may claim to take actions for you in the real world, but they may not actually do anything. Bots on SingularityLabs AI Platform may not generate accurate information, and the information they provide may be outdated. You should independently verify any responses or advice from bots on SingularityLabs AI Platform. SingularityLabs AI Platform does not guarantee the accuracy of any information provided by bots on the platform. Bots on SingularityLabs AI Platform are subject to change and may contain errors, design flaws, or other issues. Using SingularityLabs AI Platform or bots on SingularityLabs AI Platform may result in unexpected results, loss of data or communications, or other anticipated or unanticipated damage or loss to you. Bots on SingularityLabs AI Platform may not operate properly, be in final form, or be fully functional. Your access to SingularityLabs AI Platform or the bots is not guaranteed, and SingularityLabs AI Platform and the bots are provided on an "as is" basis.
        </p>

        <div class="text-left text-slate-400 sm:max-w-2xl sm:text-lg flex flex-col gap-2">
            You may not use SingularityLabs AI Platform or the bots on it to:
            <li class="list-square">
                Violate the rights of someone else or any laws.
            </li>
            <li class="list-square">
                Violate any of these Terms or our policies, or the policies of third-party providers that power the bots on SingularityLabs AI Platform, which can be found in the bot profile or by visiting https://www.merriam-webster.com/dictionary/reverse.
            </li>
            <li class="list-square">
                Try to figure out how the models, algorithms, and systems of SingularityLabs AI Platform, the bots, or their underlying technologies work by taking them apart, putting them back together, or translating them.
            </li>
            <li class="list-square">
                Abuse, harm, interfere with, reverse engineer, or disrupt SingularityLabs AI Platform, the bots, or their underlying technologies. This includes using them in a way that is fraudulent or deceptive, introducing malware, or spamming, hacking, or bypassing any security measures.
            </li>
            <li class="list-square">
                Use SingularityLabs AI Platform or the bots in an automated way, such as by exceeding any rate limits we set.
            </li>
            <li class="list-square">
                Use SingularityLabs AI Platform or the bots to develop products, applications, services, foundation models, or other large-scale models that compete with SingularityLabs AI Platform, the bots, and their underlying technologies.
            </li>
            <li class="list-square">
                Use any method to extract data from SingularityLabs AI Platform or the bots, including web scraping, web harvesting, or web data extraction methods, other than as allowed by these Terms of Service.
            </li>
            <li class="list-square">
                Say that Bot-Generated Content (defined below) is human-generated.
            </li>
        </div>


        <h3 class="text-left text-lg font-semibold text-slate-200 sm:text-2xl">
            Your Content
        </h3>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            4.1 SingularityLabs AI Platform may allow you to ask questions, create bookmarks, vote or like, post, or share bot conversations within or outside of the platform. All material you upload, publish, or display on SingularityLabs AI Platform, and any results you receive in response to your prompts (or other inputs) from bots on SingularityLabs AI Platform ("Bot-Generated Content"), will be considered "Your Content."
        </p>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            4.1 Other users may ask questions and receive responses from bots on  that are similar to or the same as yours. The content that other users receive are not considered Your Content.
        </p>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            4.2 Your Bots.  Some users may be able to create bots on SingularityLabs AI Platform that are powered by third-party large language models (LLMs), or add their own bots to the platform for other users to interact with (each called a "Your Bot"). Your Bots will be linked to your profile name. You are not required to create a bot, but if you do, you must make sure that the content is legal and does not violate these Terms, our policies, or the policies of any third-party LLMs that power your bot. SingularityLabs AI Platform may, in its sole discretion, remove your bot if it violates these Terms, our policies, the policies of any third-party LLMs that power your bot, or applicable law. SingularityLabs AI Platform is not responsible for Your Bots, any of their content, or how others use Your Bots. If you choose to connect Your Bots to SingularityLabs AI Platform using our APIs, then the API Terms apply to your use of such APIs.
        </p>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            4.3 Ownership. You retain ownership of Your Content, subject to the non-exclusive rights granted below.
        </p>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            4.4 Your Responsibility. You understand and agree that bots on SingularityLabs AI Platform answer your questions based on information from a variety of sources, and that SingularityLabs AI Platform does not create or generate any Bot-Generated Content. SingularityLabs AI Platform provides access to several underlying technologies, including third-party providers that use large language models (LLMs). An LLM is a machine learning system that processes and generates text. You agree that you are responsible for Your Content and Your Bots, including ensuring that they do not violate any applicable law, these Terms (including the Restricted Uses in Section 3.3 above), our policies, or the policies of any third-party LLMs that power bots on SingularityLabs AI Platform.
        </p>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            We reserve the right to block, remove, and/or permanently delete Your Content or Your Bots if they are in breach of these Terms, our policies, the policies of any third-party LLMs which power bots within , or violate any applicable law or regulation, or if it creates risk for  or  or negatively impacts the experience other  users.
        </p>

        <div class="text-left text-slate-400 sm:max-w-2xl sm:text-lg flex flex-col gap-2">
            4.5 Our Use of Your Content. We may use Your Content and Your Bots to provide and improve SingularityLabs AI Platform, including:
            <li class="list-square">
                Sending your questions and prompts to third-party LLMs to generate responses
            </li>
            <li class="list-square">
                Showing Your Content to others if you use the sharing features in SingularityLabs AI Platform
            </li>
            <li class="list-square">
                Making Your Bots available for others to use and interact with in SingularityLabs AI Platform
            </li>
            <li class="list-square">
                Promoting your shared content or Your Bots to others
            </li>
            <li class="list-square">
                Understanding your use of SingularityLabs AI Platform to generally improve the services
            </li>
            <li class="list-square">
                We may also need to use or disclose Your Content to comply with applicable laws, enforce these Terms of Service and our policies, and to detect and prevent fraud, security, or technical issues.
            </li>
        </div>

        <h1 class="text-left text-2xl font-semibold text-slate-200 sm:text-5xl">
            Termination
        </h1>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            You can stop using SingularityLabs AI Platform or terminate these Terms of Service at any time for any reason or no reason by deleting your account in your settings. We can also terminate your access to SingularityLabs AI Platform and/or these Terms of Service at any time for any reason or no reason. Any data collected before termination may continue to be used in accordance with these Terms.
        </p>
        <div class="text-left text-slate-400 sm:max-w-2xl sm:text-lg flex flex-col gap-2">
            The following provisions will continue to apply after these Terms expire or are terminated, in addition to the provisions set forth in Section 11(e) of the Platform Terms of Service:
            <li class="list-square">
                Section 3.4 (Feedback)
            </li>
            <li class="list-square">
                Section 4.3, 4.4, and 4.5 (Your Content)
            </li>
            <li class="list-square">
                This Section 5 (Termination)
            </li>
            <li class="list-square">
                Section 7 (Disclaimers and Limitation of Liability)
            </li>
            <li class="list-square">
                Section 8 (General)
            </li>
        </div>

        <h1 class="text-left text-2xl font-semibold text-slate-200 sm:text-5xl">
            Privacy
        </h1>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            As detailed in the Privacy Policy, we may collect certain personal information, such as contact information, related to your use of SingularityLabs AI Platform. Your account information is anonymized before being shared with third-party LLM providers and developers. The third-party developers and LLM providers may receive details about your interactions with bots on SingularityLabs AI Platform, such as the contents of your chats and upvotes, to provide responses and to generally improve the services. You do not need to share sensitive personal information, such as credit card information or social security information, with the bots. For more information about the third-party LLM providers, please see the respective bot profiles. For more information about SingularityLabs AI Platform's privacy practices, please visit the Privacy Policy.
        </p>

        <h1 class="text-left text-2xl font-semibold text-slate-200 sm:text-5xl">
            DISCLAIMERS AND LIMITATION OF LIABILITY
        </h1>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            Section 8 of the  Platform Terms of Service is incorporated herein by reference, except that Section 8(e) of the  Platform Terms of Service is replaced with the following: WITHOUT LIMITING THE FOREGOING, ’S MAXIMUM AGGREGATE LIABILITY TO YOU FOR LOSSES OR DAMAGES THAT YOU SUFFER RELATED TO OR ARISING OUT OF YOUR USE OF THE  SERVICES OR THESE TERMS IS LIMITED THE AMOUNT YOU PAID TO  IN THE PRIOR TWELVE (12) MONTHS FOR THE  SERVICES GIVING RISE TO THE CLAIM.
        </p>
        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            WE CANNOT GUARANTEE THE AVAILABILITY OF ANY BOTS, FEATURES OR SERVICE OF  OR AVAILABLE THROUGH . WHILE WE ARE CONTINUING TO DEVELOP NEW FEATURES, ADD BOTS AND IMPROVE , WE MAY, WITHOUT NOTICE TO YOU, ADD OR REMOVE FEATURES OR BOTS, LIMIT USE OR AVAILABILITY OF FEATURES OR BOTS ENTIRELY (OR JUST IN CERTAIN PLACES OR FOR SOME USERS) IF THEY CREATE RISK TO , USERS OF , THIRD PARTIES POWERING THE BOTS, NO LONGER MAKE SENSE FROM A BUSINESS PERSPECTIVE OR FOR ANY REASON IN OUR SOLE DISCRETION. WE ALSO CANNOT GUARANTEE THAT YOUR USE OF  WILL BE ERROR FREE, DISRUPTED OR THAT YOU WILL NOT EXPERIENCE SERVICE OUTAGES. WE ARE NOT LIABLE FOR ANY ERRORS, DISRUPTIONS OR SERVICE OUTAGES THAT MAY OCCUR.
        </p>

        <h1 class="text-left text-2xl font-semibold text-slate-200 sm:text-5xl">
            General
        </h1>

        <p class="text-left text-slate-400 sm:max-w-2xl sm:text-lg">
            You agree that any claim not subject to Arbitration as set forth in Section 10 of the  Platform Terms of Service must be resolved in a competent court in Santa Fransisco, California and that the substantive laws of the State of California in the United States of America (excluding conflict of laws rules) will govern these Terms and any claim. These Terms will be binding upon and will inure to the benefit of your and our heirs, successors, and/or assignees.
        </p>
    </div>
</section>