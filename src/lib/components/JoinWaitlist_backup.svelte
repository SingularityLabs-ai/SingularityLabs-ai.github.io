
    <div class="flex flex-col gap-5">
        <form method="POST" action="https://script.google.com/macros/s/AKfycbyhhb7ueo1PTnhUqTEMXBITXSPji7V8soD21LXm9IYZXzb_0Ffm30wUlu8eh1fuYuSi/exec" id="myform">
            <div class="flex flex-col gap-4">
                <Input placeholder="Your Name" name="Name" type="text" bind:value={name}>
                <Input placeholder="Your Email" name="Email" type="email" bind:value={email}>
            </div>
            <button class="ring-ring-500 rounded-full bg-green-600 px-8 py-3 font-medium text-green-200 ring-1 ring-green-500 transition-all duration-500 hover:bg-green-500" type="submit" on:click={async () => { alert('Thank you for joining the waitlist! We will notify you when SingularityLabs Cloud is ready for you.'); }}>Subscribe!</button>
        </form>
    </div>