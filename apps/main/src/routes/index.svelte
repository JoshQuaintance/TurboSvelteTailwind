<script lang="ts">
    import { readable } from 'svelte/store';

    import { Counter } from '@template/components';

    const formatter = new Intl.DateTimeFormat('en', {
        hour12: true,
        hour: 'numeric',
        minute: '2-digit',
        second: '2-digit'
    });

    const time = readable(new Date(), function start(set) {
        const interval = setInterval(() => {
            set(new Date());
        }, 1000);

        return function stop() {
            clearInterval(interval);
        };
    });
</script>

<div class="flex flex-col justify-around items-center dark:bg-gray-900 dark:text-white leading-loose h-screen pb-24">
    <span class="text-8xl font-bold mb-10"
        >Hello <br />
        <a href="https://kit.svelte.dev" target="_blank"
            ><span id="sveltekit" class="bg-clip-text bg-gradient-to-r text-transparent">SvelteKit</span></a>
        <br />
        <a href="https://tailwindcss.com" target="_blank"
            ><span id="tailwind" class="bg-clip-text bg-gradient-to-r text-transparent">Tailwind</span></a>
        <br />

        <a href="https://turborepo.com" target="_blank"
            ><span id="turborepo" class="bg-clip-text bg-gradient-to-r text-transparent">Turborepo</span></a
        >!
    </span>

    <h1 class="text-2xl">The local time is {formatter.format($time)}</h1>

    <Counter />

    <span> Click on the text to learn more about each technology </span>
</div>

<style lang="postcss">
    #sveltekit {
        @apply cursor-pointer;
        @apply from-[#FE5858] via-[#FC9842] to-[#eb9927];
    }

    #tailwind {
        @apply cursor-pointer;
        @apply from-green-400 via-blue-500 to-indigo-500;
    }

    #turborepo {
        @apply cursor-pointer;
        @apply from-[#ef4444] to-[#3b82f6];
    }
</style>
