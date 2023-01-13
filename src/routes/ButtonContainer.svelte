<script>
	import CalcButton from "./CalcButton.svelte";

    // 10 items in the array from (9-0)
    let calcnums = [...Array(10).keys()].reverse();
    calcnums.splice(9, 0, "pi")
    calcnums.splice(11, 0, ".")
    export let numClick;
    export let operatorClick;
    export let equalsClick;
    export let clearClick;
</script>

<style>
    .all-buttons {
        min-height: 50%;
        width: 100%;
        height: max-content;
        display: grid;
        grid-template-columns: 75% 25%;
    }
    
    .num-buttons {
        justify-items: center;
        align-items: center;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
    }
    
    .operator-buttons {
        justify-items: center;
        align-items: center;
        display: grid;
        
    }

    .equal-button {
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>

<div class="all-buttons">
    <div class="num-buttons">
        {#each calcnums as calcnum}
            <CalcButton title={calcnum} onClick={() => numClick(calcnum)}/>
        {/each}
    </div>
    
    <div class="operator-buttons">
        <CalcButton title="+" onClick={() => operatorClick("+")}/>
        <CalcButton title="-" onClick={() => operatorClick("-")}/>
        <CalcButton title="×" onClick={() => operatorClick("*")}/>
        <CalcButton title="÷" onClick={() => operatorClick("/")}/>
    </div>

    <div class="equal-button">
        <CalcButton title="=" onClick={() => equalsClick()} overrideWidth={true}/>
    </div>

    <div class="operator-buttons">
        <CalcButton title="CE" onClick={() => clearClick()}/>
    </div>
</div>