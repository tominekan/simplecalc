<script>
	import ButtonContainer from "./ButtonContainer.svelte";
	import CalcEntry from "./CalcEntry.svelte";
    let calcinput = "1+1";

    function addToInputBar(input) {
        calcinput+=input;
    }

    function clearInputBar() {
        calcinput = "";
    }

    function solveInputBar() {
        try {
            calcinput = String(eval("let pi=3.141592653589793238462643;" + calcinput));
        } catch (error) {
            alert("Incorrect Input");
        }
    }
</script>

<style>
    :global(body) {
        margin: 0;
        padding: 0;
        border: 0;
        height: 100vh;
        width: 100vw;
        max-width: 100%;
        background-color: #f9fdf7;
        box-sizing: border-box;      
    }

    :global(html) {
        margin: 0;
    }

    .calculator {
        margin: 0;
        padding: 0;
        height: 100%;
        width: 100%;
        /* display: flex;
        border: 1px solid;
        flex-direction: column;
        align-items: center;
        justify-content: center; */
        background-color: white;
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
    }
</style>

<title>Simple Calculator</title>
<div class="calculator">
    <CalcEntry input={calcinput} />
    <ButtonContainer
        numClick={addToInputBar}
        operatorClick={addToInputBar}
        equalsClick={solveInputBar}
        clearClick={clearInputBar}
        />
</div>
