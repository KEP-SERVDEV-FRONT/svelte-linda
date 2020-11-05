<script> 

	let card = [
		{ id: '0', name: '🍇' },
		{ id: '1', name: '🍈' },
        { id: '2', name: '🍉' }
    ];

</script>

<section>
    🍇 🍈 🍉 🍊 🍋 🍍   

    <ul class="cklist">
        {#each card as { id, name }, i}
            <li>
                <input type="checkbox" id="{id}">
                <label for="{id}">{name}</label>
            </li>
        {/each}
    </ul>

</section>

<section>
    <ul>
        <li>
            <div></div>     
        </li>
    </ul>
</section>

<style>
    .cklist{display: flex;align-content: center;justify-content: center;line-height:100px;}
    .cklist li{position: relative;padding:0 20px;font-size:50px;text-align: center;}
    .cklist input{position: absolute;top:50%;left:50%;opacity: 0;}
    .cklist label{display:inline-block;position: relative;width:100px;height:100px;border:3px solid rgb(120, 154, 65);z-index:10;opacity:.7;cursor: pointer;box-sizing:border-box}
    /* .cklist label:hover{opacity: 1;} */
    .cklist input:checked + label{border:3px solid rgb(213, 57, 57);opacity: 1;}
</style>



<div style="padding:30px;white-space: pre-line;line-height:2;color:#666;font-size:15px">

    // 2020.11.05. 짝맞추기 게임
    + 과일 랜덤 세팅 + 
    카드 리스트에 원하는 과일을 골라 li 배열에 담는다 
    과일을 선택하고 확인을 누르면 리스트는 사라지고 세팅한 카드들이 나열된다. 
    ㅡ 선택하는 과일 리스트 - 초기값 -> 체크박스로 선탁하자. 
    ㅡ ㅡ 체크박스 id 값과 for값을 배열값으로 나열

    과일 갯수X2로 맞추기 카드들이 나열된다. 
    ㅡ 선택한 과일 리스트 x 2 - 카드들로 나열 (위치는 랜덤으로 뿌려진다)

    + 게임 로직 +
    처음에 카드들이 세팅될때 앞면이 먼저 보여지며 차례대로 카드가 뒤집어 진다. 
    원하는 카드를 선택 동일한 과일 카드가 나올 경우 오픈된 상태로 된다. 

    + 게임룰 +
    과일을 고른 갯수에 따라 초 시간이 분배된다 
    ex) 과일 5개 고르면 10초를 곱해 50초 동안 게임을 진행한다 . -> 추후 난이도 조절에 따라 곱한 초 시간 / 난이도 상중하 값을 나눈다. 
    

</div>