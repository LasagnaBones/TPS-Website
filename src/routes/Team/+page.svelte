<script lang="ts">
    const people: Record<string, { description: string; img: string; role: string }> = {
        "Boykisser": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing men.",
            img: "/boykisser.png",
            role: "The Charm"
        },
        "Alan Turing": {
            description: "Father of modern computing.",
            img: "https://upload.wikimedia.org/wikipedia/commons/a/a1/Alan_Turing_Aged_16.jpg",
            role: "Gay Programmer"
        },
        "bikisser": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing everyone.",
            img: "/boykisser.png",
            role: "The Bisexual"
        },
        "malekisser": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing men.",
            img: "/boykisser.png",
            role: "The Thinker"
        },
        "mankisser": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing men.",
            img: "/boykisser.png",
            role: "The Heavy"
        },
        "ladkisser": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing men.",
            img: "/boykisser.png",
            role: "The Scout"
        },
        "kisser": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing men.",
            img: "/boykisser.png",
            role: "The Scout"
        },
        "fukc": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing men.",
            img: "/boykisser.png",
            role: "The Scout"
        },
        "ufkc": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing men.",
            img: "/boykisser.png",
            role: "The Scout"
        },
        "men": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing men.",
            img: "/boykisser.png",
            role: "The Scout"
        },
        "girlksiser": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing girl.",
            img: "/boykisser.png",
            role: "The Scout"
        },
        "pookie": {
            description: "The heart and soul of TPS. Brings joy to everyone and loves kissing men.",
            img: "/boykisser.png",
            role: "The Scout"
        }
    };
</script>


<div class="people-holder">
    <ul>
    {#each Object.entries(people) as [name, person]}
        <li>
            <h2 class = "name">{name}</h2>
            <div class="horizontal"> 
                <div class="vertical">
                    <img src="{person.img}" alt="{name}" width="100%" class = "headshot" />
                    <em class = "role">{person.role}</em>
                </div>  
                <div class="vertical">
                    <p class = "description">{person.description}</p>
                </div>  
            </div>
        </li>
    {/each}    
    </ul>

<div class = "person">

</div>






</div>

<style lang="css">
    .people-holder{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center; /* Ensures the container itself is centered */
        max-width: 1200px; /* Set a reasonable max-width */
        width: 90%; /* Makes it responsive */
        margin: 0 auto; /* Centers horizontally */
    }
    .people-holder ul{
        flex-wrap: wrap;
        list-style: none;
        display: flex;
        justify-content: center; /* Centers items horizontally */
        gap: 15px; /* Adds spacing between items */
        padding: 0;
        max-width: 100%; /* Ensures it doesn't overflow */

    }
    .people-holder li {
        background: white;
        display: flex;
        flex-direction: column;
        align-items: center; /* Centers content inside */
        min-width: 200px;
        width: 25%;
        margin: 10px;
        border: 7px solid rgb(66, 66, 66);
        border-radius: 10px;
        overflow: hidden; 
        padding: 15px; /* Prevents content from touching the edges */
        box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.2); /* Optional: Adds depth */
        text-align: center; /* Centers text */
    }
    .horizontal {
        display: flex;
        flex-direction: row;
        overflow-wrap: normal;

    }
    .vertical {
        display: flex;
        margin: 10px;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        width: 100%;
        height: 100%;
    }
    .name {
        margin: 0px auto;
    }
    .role{
        text-align: center;
        margin-top: 5px;
    }
    .headshot {
        margin: 0 auto;

    }

</style>