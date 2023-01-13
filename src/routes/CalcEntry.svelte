<style>
    @import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,500;0,700;0,900;1,400;1,500;1,700;1,900&display=swap');
    .calc-input {
        width: 98%;
        min-height: 15%;
        background: none;
        border: none;
        font-family: "Roboto", sans-serif;
        font-size: xx-large;
        font-weight: bolder;
        padding-left: 10px;
        box-sizing: border-box;
        
    }

    .calc-input:active {
        border: 0;
        outline: none;
    }
</style>

<script>
    export let input = "3";
</script>

<input
    aria-label="calc input"
    type="text"
    name="Calc Input"
    class="calc-input"
    value={input}
    readonly
    >