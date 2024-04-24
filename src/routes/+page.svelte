<script>
    import Counter from './Counter.svelte';
    import welcome from '$lib/images/svelte-welcome.webp';
    import welcome_fallback from '$lib/images/svelte-welcome.png';
    import robot_img from '$lib/images/LynxKasselRobot/IMG_6507.jpg';
    import programming_img from '$lib/images/PhotoTastatur.jpg';
    import design_img from '$lib/images/RandomDesign.jpeg';
    import greece_img from '$lib/images/Greece.jpg';

    let interests = ['Robotics', 'Programming', 'Design'];
    let images = [robot_img, programming_img, design_img]
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
        <section class="card">
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
        color: var(--base-100);
        background: var(--base-content);
        opacity: 0.6;
		background-size: auto;
		background-position: center;
		background-blend-mode: soft-light;
        transition: opacity 0.1s ease-in-out, border 0.1s ease-in-out;
    }

    .card:hover {
        border: 5px solid var(--accent);
        border-radius: 10px;
        opacity: 1;
    }

</style>
