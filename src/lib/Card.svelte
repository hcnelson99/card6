<script>
    export let title;
    export let cardType;
    export let rules;
    export let mana;
    export let power;
</script>

<div class=wrapper>
    <div class="border titlebar" >
        <div class=title class:untitled={!title}>
            {title || 'Card Title'}
        </div>
        {#if mana}
            <div class="border mana">{mana}</div>
        {/if}
    </div>
    <canvas class=border width="246" height="180"></canvas>
    <div class=border class:untitled={!cardType}> 
        {cardType || 'Card Type'}
    </div>
    <div class="rules border grow"> 
        <div class:untitled={!rules}>
            {rules || 'Rules'} 
        </div>

        {#if power}
            <div class="border power">{power}</div>
        {/if}
    </div>
</div>

<style>
    .wrapper {
        width: 250px;
        height: 350px;
        border-radius: 12px;
        border: 12px solid black;
        padding: 6px;
        display: flex;
        flex-direction: column;
    }

    .border + .border {
        border-top: 0;
    }

    .border {
        border: 2px solid black;
        padding: 4px;
    }

    .untitled {
        font-style: italic;
    }

    .grow {
        flex-grow: 1;
    }

    .rules {
        position: relative;
    }

    .titlebar {
        position: relative;
    }

    .mana {
        position: absolute;
        top: 0;
        right: 0em;
        border-right: 0;
        border-bottom: 0;
        border-top: 0;
    }


    .power {
        position: absolute;
        bottom: 0;
        right: 0;
        border-right: 0;
        border-bottom: 0;
    }

    canvas {
        display: block;
    }

</style>
