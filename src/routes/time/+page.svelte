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

    let interests = ['Me Now', 'Robotics', 'Programming', 'Design'];
    let texts = [
        /* SCHOOL */
        "I'm currently in a german high-school and going to make my Abitur in summer 2023.\n" +
        "I spend most of my time programming in robotics, app development, web development and plugin development.",
        /* ROBOTICS */
        "Since 2022 I work with three colleagues in the Bodenseeluchse (Lynx Robotics) Team for the robocup 2v2" +
        "Lightweight League. \nWe got last year the second place on the german open in Kassel and the fifth place as well " +
        "as the \"outstanding design award\" and the \"best poster and presentation award\" on the World Cup 2023 in " +
        "Bordeaux.\n This year (23/24) we got the first place at the german open in Kassel and are going to participate " +
        "in the world championship in Eindhoven.\n (For more information double-click)",
        /* PROGRAMMING */
        "I started programming with Python in the SFZ Friedrichshafen. \nIn the Corona-Lockdown I made a online Java " +
        "course after which I went to our schools robotics club and started writing abstract code for tactics " +
        "and calculations. \nBeside robotics I have little experience in Android Kotlin (Jetpack Compose), and Plugin " +
        "Development for XPlane. \n",
        /* DESIGN */
        "I'm sometimes designing in Fusion, but not a great enthusiast. I got some humorous designs on my Printables account."];
    let images = [robot_img, programming_img, design_img]
    let links = ["", "https://www.lynx-robotics.org", "", "https://www.printables.com/de/@MatthesNeuman_747832"];

    let show_extra = 0;

    function handle_db_click(i) {
        window.location.href = links[i];
    }
</script>

<svelte:head>
    <title>Zeitformatierung</title>
    <meta name="description" content="Zeitformatierung"/>
</svelte:head>
<section class="card">
    Im Moment ist es vermutlich das Sinnvollste den Julianischen Kalender als solches zu übernehmen.<br><br>
    Zeit sollte jedoch für ihre Lesbarkeit und Einschätzbarkeit im Dezimalsystem absteigend angegeben werden. <br><br>
    Rückwärtsläufigkeit erhöht die Produktivität.<br><br>
    Umstellungen von Winter- und Sommerzeit sind nicht berücksichtigungswürdig, wobei ich empfehle sich an die Umwelt anzupassen.<br><br>
    <br>
    YYYY'MMDDT<br>
    2023'0311'3.0<br>

    Gängig: 11.03.2023, 07:12Uhr<br>
</section>

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
