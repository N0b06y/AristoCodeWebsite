<script>
    import welcome from '$lib/images/svelte-welcome.webp';
    import welcome_fallback from '$lib/images/svelte-welcome.png';
    import robot_img from '$lib/images/LynxKasselRobot/IMG_6507.jpg';
    import programming_img from '$lib/images/PhotoTastatur.jpg';
    import design_img from '$lib/images/RandomDesign.jpeg';
    import greece_img from '$lib/images/Greece.jpg';
    import {blur} from 'svelte/transition';
    import {fly} from 'svelte/transition';
    import {fade} from 'svelte/transition';
    import {crossfade} from 'svelte/transition';
    import {slide} from 'svelte/transition';
    import {scale} from 'svelte/transition';
    import {draw} from 'svelte/transition';

    let _time_text =
        "Im Moment ist es vermutlich das Sinnvollste den Julianischen Kalender als solches zu übernehmen.<br><br>" +
        "    Zeit sollte jedoch für ihre Lesbarkeit und Einschätzbarkeit im Dezimalsystem absteigend angegeben werden. <br><br>" +
        "    Rückwärtsläufigkeit erhöht die Produktivität.<br><br>" +
        "    Umstellungen von Winter- und Sommerzeit sind nicht berücksichtigungswürdig, wobei ich empfehle sich an die Umwelt anzupassen.<br><br>" +
        "    <br>" +
        "    YYYY'MMDDT <br>" +
        "    2023'0311'3.0 <br> " +
        "    Gängig: 11.03.2023, 07:12Uhr<br>";

    let time_text = "Im Moment ist es vermutlich das Sinnvollste den Julianischen Kalender als solches zu übernehmen.<br><br>" +
        "Zeit sollte jedoch für ihre Lesbarkeit und Einschätzbarkeit im Dezimalsystem absteigend angegeben werden. Rückwärtsläufigkeit erhöht die Produktivität.<br><br>" +
        "Umstellungen von Winter- und Sommerzeit sind nicht berücksichtigungswürdig, wobei ich empfehle sich an die Umwelt anzupassen.<br><br>" +
        "YYYY'MMDDT<br><br>" +
        "2023'0311'3.0<br><br>" +
        "Gängig: 11.03.2023, 07:12Uhr<br><br>";

    let show_extra = true;

    let time = new Date()
    let seconds;
    let clock = '';

    setInterval(() => {
        time = new Date();
    }, 1000);

    $: seconds = time.getHours() * 3600 + time.getMinutes() * 60 + time.getSeconds();
    $: clock = (10 - ((seconds / 8640) % 100)).toFixed(5);
</script>

<svelte:head>
    <title>Zeitformatierung</title>
    <meta name="description" content="Zeitformatierung"/>
</svelte:head>

{#if show_extra}
    <section class="card" role="button" tabindex="0"
             on:click={()=>{show_extra=!show_extra}}
             on:keydown={()=>{}}
             transition:slide
    >
        {@html time_text}
    </section>
{:else }
    <section class="fill_card" role="button" tabindex="0"
             on:click={()=>{show_extra=!show_extra}}
             on:keydown={()=>{}}
             transition:slide
    >
        <h1>
            {@html clock}
        </h1>
    </section>
{/if}

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

    .fill_card {

        width: 60%;
        height: 60%;

        border-radius: 15px;
        border: 2px solid rgb(255, 255, 255, 0.4);
        /*border: 2px solid rgb(0, 0, 0, 0.8);*/
        padding: 10px;
        margin: 10px;
        color: var(--base-100);
        background: var(--base-content);
        opacity: 0.8;
        background-size: cover;
        background-position: center;
        background-blend-mode: soft-light;
        transition: opacity 0.2s ease-in-out 0.2s, border 0.2s ease-in-out;

        justify-content: center;
        display: flex;
        position: absolute;
        align-self: center;
        text-align: center;
        top: auto;
        left: auto;
        /*z-index: 1000;*/
        font-weight: bold;
        font-size: 5em;
        font-style: normal;
        font-family: "Roboto", monospace;
    }

    .card {
        border-radius: 15px;
        border: 2px solid rgb(255, 255, 255, 0.4);
        /*border: 2px solid rgb(0, 0, 0, 0.8);*/
        padding: 10px;
        margin: 10px;
        color: var(--base-100);
        background: var(--base-content);
        opacity: 0.8;
        background-size: auto;
        background-position: center;
        background-blend-mode: soft-light;
        transition: opacity 0.2s ease-in-out 0.2s, border 0.2s ease-in-out;

        flex-direction: column;
        justify-content: start;
        display: -webkit-flex;
        width: 87.915%;

    }

    .card:hover {
        /*border: 2px solid var(--base-100);*/
        /*border-radius: 10px;*/
        opacity: 0.9;
    }

    /*.glas {*/
    /*    width: 87.915%;*/
    /*    border-radius: 15px;*/
    /*    border: 2px solid rgb(255, 255, 255, 0.4);*/
    /*    padding: 0.781dvw;*/
    /*    background-color: rgb(255, 255, 255, 0.2);*/
    /*    display: flex;*/
    /*    flex-direction: row;*/
    /*    justify-content: start;*/
    /*    align-items: center;*/
    /*}*/


</style>
