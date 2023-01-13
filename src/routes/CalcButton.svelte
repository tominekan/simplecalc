<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,500;0,700;0,900;1,400;1,500;1,700;1,900&display=swap');
    button {
        margin: 10px;
        border: 1px solid black;
        min-height: 60px;
        min-width: 85px;
        width: 90%;
        height: 85%;
        background-color: white;
        font-family: "Roboto", sans-serif;
        font-size: large;
    }

    button:hover {
        background-color: #eefae7;
    }

    .widened {
        width: calc(90% + calc(25% * 0.256));
    }

</style>


<script>
    export let title = "default";
    export let onClick;
    export let overrideWidth = false;
</script>
{#if overrideWidth}
<button on:click={onClick} class="widened">{title}</button>
{:else}
<button on:click={onClick}>{title}</button>
{/if}