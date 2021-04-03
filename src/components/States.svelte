<script>
    import states from '../data/states-data.json';
    
    let isVisible=true;
    let statesSelected = [];    
</script>

<style>
    input.right {
        float: right;
    }
    div {
        display: grid;
        grid-template-columns: auto auto auto;
        padding: 10px;        
    }
    .hidden {
        display: none;
    }
</style>
<input type="button" value="Hide" class="right" on:click="{(e)=>{ isVisible=!isVisible; e.eventTarget.value=isVisible?'Hide':'Show';}}"/>
<div class:hidden="{isVisible===true}">
    {#each states as state}
        <div>
            <span>
                <input type="checkbox" value={state.shortName} bind:group="{statesSelected}">
                {state.longName}
            </span>
        </div>
    {/each}
</div>
<div>{statesSelected}</div>
