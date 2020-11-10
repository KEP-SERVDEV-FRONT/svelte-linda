<!-- 기본 카드 틀
클릭하면 돌아간다 
멈춘다 
카드값을 담는다 -->

<script>
    export let current;
    const initial = current;

    // const initial = [
    //     {

    //     },
    // ];
</script>

<!--   on:click={() => SEND({initial})}  -->
<button class="card" style="background-color:{initial}" >
    여기에 카드 종류가 뿌려집니다
</button>

<style lang="scss">
.card{
    flex:none;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width:200px;height:350px;
    margin: 20px;
    border-radius:5px;
    border:6px solid rgb(155, 29, 29); 
    color:#fff;
    text-align: center;
    &:hover{
        border:6px solid black;
    }
}

</style>