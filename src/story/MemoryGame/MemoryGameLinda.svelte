<script>
    import MemoryGameCard from "./MemoryGameCard.svelte"
    
    // 카드에 값을 넣는다
    let cards = [
		{ id: 1, card: '#0d0887' },
		{ id: 2, card: '#6a00a8' },
		{ id: 3, card: '#b12a90' },
		{ id: 4, card: '#e16462' },
        { id: 5, card: '#fca636' },
        { id: 6, card: '#0d0887' },
		{ id: 7, card: '#6a00a8' },
		{ id: 8, card: '#b12a90' },
		{ id: 9, card: '#e16462' },
		{ id: 10, card: '#fca636' }
    ]; 

    // 카드에 랜덤으로 컬러값을 넣는다.  
    cards = cards.slice().sort(() => Math.random() > 0.5 ? 1 : -1)
    
    function openCard (card){
        card = card
        if ( card === card ) print = "카드 같은값이다"

    }

</script>
    
<div class="card_list">

    {#each cards as thing (thing.id)}
         <MemoryGameCard current={thing.card}/>
    {/each}

    {print}

</div>
<style lang="scss">
    .card_list{display: flex;flex-wrap:wrap;}
</style>



<!-- https://dororongju.tistory.com/103 로직 따라하고 싶음 -->