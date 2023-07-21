<script>
    import Card from '$lib/Card.svelte';

    let title;
    let cardType;
    let rules;
    let mana;
    let power;
</script>

<div class=wrapper>
    <form>
        <label> 
            Title: 
            <input bind:value={title}> 
        </label>
        <label> 
            Card Type: 
            <input bind:value={cardType}> 
        </label>
        <label> 
            Rules: 
            <textarea bind:value={rules}></textarea>
        </label>
        <label> 
            Mana: 
            <input bind:value={mana}> 
        </label>
        <label> 
            Power: 
            <input bind:value={power}> 
        </label>
    </form>
    <Card {title} {cardType} {rules} {mana} {power} />
</div>


<style>
    .wrapper {
        display: flex;
    }

    label {
        display: block;
    }
</style>

