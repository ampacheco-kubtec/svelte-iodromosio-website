<script>
    import {states} from '../data/states.js';
    let isVisible=true;
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

<input type="button" value="Hide" class="right" on:click="{()=>isVisible=!isVisible}"/>
<div class:hidden="{isVisible===true}">
    {#each states as state}
        <div>
            <span>
                <input type="checkbox">
                {state.longName}
            </span>
        </div>
    {/each}
</div>
