<script>
    import { onMount } from 'svelte';

    const randomBetween = (min, max) => Math.round(Math.random() * max) + min;
    let x = '0';
    let y = '0';

    let interval;

    onMount(() => {
        clearInterval(interval);
        interval = setInterval(() => {
            x = `${randomBetween(0, window.innerWidth)}px`;
            y = `${randomBetween(0, window.innerHeight)}px`;
        }, 900);
    });
</script>
<div class="container" >
    <div class="box" style="--x: {x}; --y: {y};"></div>
</div>

<style>
    .container {
        display: flex;
        gap: 10px;
        flex-wrap: wrap;
    }

    .box {
        --x: 50;
        --y: 20;
        display: block;
        position: absolute;
        top: 0;
        left: 0;
        width: 100px;
        height: 100px;
        background: teal;
        transform: translate(var(--x), var(--y)) translateZ(0);
        transition: all 700ms ease;
    }
</style>
