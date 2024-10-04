<script>
    import img1Src from "$lib/assets/collage-1.png";
    import img2Src from "$lib/assets/collage-2.png";
    import img3Src from "$lib/assets/collage-3.png";
    import img4Src from "$lib/assets/collage-4.png";

    import { animate, inView } from "motion";
	import { onMount } from "svelte";

    onMount(() => {
        // inView("header > div img:first-of-type", ({ target }) => {
        //     animate(target, { scale: [.5, 1], opacity: [0, 1], translateX: ["-50%", "0"] }, { duration: .750 });
        // }, { margin: "-300px 0px" })

        // inView("header > div img:last-of-type", ({ target }) => {
        //     animate(target, { scale: [.5, 1], opacity: [0, 1], translateX: ["50%", "0"] }, { duration: .750 ,delay: .2 });
        // }, { margin: "-300px 0px" })

        inView("header > div img", ({ target }) => {
            animate(target, { scale: [.5, 1], opacity: [0, 1], translateY: ["70%", "0"] }, { duration: .750 });
        }, { margin: "-300px 0px" })
    })
</script>

<main>
    <header>
        <p>Redefining the California Shutter</p>
        <div>
            <img src="{img1Src}" alt="">
            <img src="{img2Src}" alt="">
        </div>
        <div class="shifted">
            <img src="{img3Src}" alt="">
            <img src="{img4Src}" alt="">
        </div>
        <div>
            <img src="{img1Src}" alt="">
            <img src="{img2Src}" alt="">
        </div>
        <div class="shifted">
            <img src="{img3Src}" alt="">
            <img src="{img4Src}" alt="">
        </div>
        <div>
            <img src="{img1Src}" alt="">
            <img src="{img2Src}" alt="">
        </div>
        <div class="shifted">
            <img src="{img3Src}" alt="">
            <img src="{img4Src}" alt="">
        </div>
    </header>
    <div class="content"></div>
</main>

<style>
    main {
        min-height: 100vh;
        background-color: #182D38;
        color: white;
    }

    img {
        /* scale: .5; */
        opacity: 0;
    }

    header {
        min-height: 200vh;
        position: relative;
        max-width: 100vw;
        /* overflow: hidden; */

        padding-block: 3rem;
        padding-inline: 12rem;
    }

    header > p {
        position: sticky;
        padding-top: 25%;
        text-align: center;
        top: 0;
        font-size: 3.29rem;
        z-index: 2;
        mix-blend-mode: difference;
    }

    header > div {
        display: flex;
        justify-content: space-between;
        gap: 5rem;
        margin-bottom: 6rem;
    }

    header > div:not(.shifted) {
        translate: 10% 0;
    }

    .shifted {
        translate: -10% 0;
    }

    .content {
        min-height: 100vh;
        border-top: 1px solid white;
    }

    @media (max-width: 1000px) {
        header {
            padding-inline: 2rem;
        }

        header > p {
            font-size: 1rem;
            padding-top: 90%;
        }

        img {
            width: 50%;
            object-fit: cover;
        }
    }
</style>