<script lang="ts">
    import Background from "./Background.svelte";
    let name = "";
    //<!--", BlauFx";-->
    let num = name.length;
    let textToDisplay = name;
    let increment = false;

    const writer = setInterval(changeName, 350);

    function changeName() {
        if (increment == true) {
            if (textToDisplay.length == name.length - 1)
                clearInterval(writer);
            textToDisplay += name[num];
            num++;
        }
        else 
        {
            if (textToDisplay.length == 1)
                increment = true;
            textToDisplay = textToDisplay.slice(0, -1);
            num--;
        }
    }
</script>

<h1>Welcome{textToDisplay}!</h1>
<svelte:window on:load|once={() => writer}></svelte:window>

<Background />
<!-- <img alt="BlauFx's logo" src="1-sw.png" />-->

<br>
<p>
Hey there! I'm BlauFx, 19 y/o.<br>
I try to use my time as efficiently/productively as possible, which sadly doesn't work out quite as often as I would like it to.<br>
Nevertheless, I strive improve myself and I would like to receive criticism about things that I could improve on.<br>
<br>
I'm a full-time Linux enthusiast (I use EndeavourOS).<br>
In my free time I play video games, develop stuff, watch anime, try to make some AMVs, or tinker around with Linux.<br>
I am interested in a variety of areas, starting from web development, cybersecurity, games, reverse engineering over to kernel development.<br></p>
