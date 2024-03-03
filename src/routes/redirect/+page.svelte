<script lang="ts">
    import { page } from '$app/stores';
    import { browser } from '$app/environment';

	let info = [
		{text: "ask", url: "https://dontasktoask.com"},
		{text: "hello", url: "https://nohello.net/en/"},
		{text: "try", url: "https://tryitands.ee"}]

	const param = $page.url.searchParams;
	const str = param.toString().slice(0, -1);
	for (const element in info) {
		if (info[element].text == str) {
			if (browser) {
			    window.location.href = info[element].url;
			}
			break;
		}
	}

</script>

<p>I will list here some useful links for interacting with people. In case I get the feeling someone wastes my or even their own time with useless stuff. </p>

{#each info as {text, url}, _}
    {text}: <a href={text}>{url}</a>
    <br>
{/each}

<br> how to use: /redirect?name
