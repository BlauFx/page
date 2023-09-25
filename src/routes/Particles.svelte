<script>
    let m = { x: 0, y: 0 };
</script>

<span></span>

<div
	on:pointermove={(e) => {
		m = { x: e.clientX, y: e.clientY };
	}}>{m.x}
</div>

<style>
    span {
        height: 25px;
        width: 25px;
        background-color: rgb(255, 0, 0);
        border-radius: 50%;
        display: inline-block;
    }
</style>