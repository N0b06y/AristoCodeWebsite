<script>
    import Counter from './Counter.svelte';
    import welcome from '$lib/images/svelte-welcome.webp';
    import welcome_fallback from '$lib/images/svelte-welcome.png';

    let interests = ['Robotics', 'Programming', 'Design'];
    let images = ['src/lib/images/LynxKasselRobot/IMG_6507.jpg', 'src/lib/images/PhotoTastatur.jpg', 'src/lib/images/RandomDesign.jpeg']
    let links = ["https://www.lynx-robotics.org", "", ""];
</script>

<svelte:head>
    <title>Home</title>
    <meta name="description" content="Me Now"/>
</svelte:head>

<section>
    <h1>
        Me Now
    </h1>
</section>

{#each interests as interest, i }
    <a href="{links[i]}">
        <section class="card" style="background-image: url({images[i]});">
            <h2 >{interest}</h2>
        </section>
    </a>
{/each}


<style>
    section {
        display: compact;
        justify-content: center;
        align-items: center;

    }

    h1 {
        width: 100%;
    }

	h2 {
		font-weight: bold;
		font-size: 1.5em;
	}

    .card {
        border-radius: 10px;
        padding: 10px;
        margin: 10px;
        color: var(--dim-base-100);
        background: var(--dim-base-content);
        opacity: 0.6;
		background-size: auto;
		background-position: center;
		background-blend-mode: soft-light;
    }
</style>
