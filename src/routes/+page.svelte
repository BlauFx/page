<script lang="ts">
    import Background from "./Background.svelte";
    let name = "BlauFx";
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

<h1>Welcome, {textToDisplay}!</h1>
<svelte:window on:load|once={() => writer}></svelte:window>

<Background />
<!-- <img alt="BlauFx's logo" src="1-sw.png" />-->
