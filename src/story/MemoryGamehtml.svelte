시작하기 버튼 
5초동안 미리 보기 
게임 스타트
틀리면 흔들

<script>
  // 엘로디 특강. 이해하기
  // 변수초기화 = []배열 { 키 : 값 }객체
  let cards = [ 
    {
      "id": 0,
      "value": "🍇",
      "show" : false,
      "done" : false
    },
    {
      "id": 1,
      "value": "🍈",
      "show" : false,
      "done" : false
    },
    {
      "id": 2,
      "value": "🍉",
      "show" : false,
      "done" : false
    },
    {
      "id": 3,
      "value": "🍊",
      "show" : false,
      "done" : false
    },
    {
      "id": 4,
      "value": "🍋",
      "show" : false,
      "done" : false
    },
    {
      "id": 0,
      "value": "🍇",
      "show" : false,
      "done" : false
    },
    {
      "id": 1,
      "value": "🍈",
      "show" : false,
      "done" : false
    },
    {
      "id": 2,
      "value": "🍉",
      "show" : false,
      "done" : false
    },
    {
      "id": 3,
      "value": "🍊",
      "show" : false,
      "done" : false
    },
    {
      "id": 4,
      "value": "🍋",
      "show" : false,
      "done" : false
    }
  ]

  // 태오가 한거고... 랜덤.. 이해못한거.
  // cards = cards.slice().sort(() => Math.random() > 0.5 ? 1 : -1)
  

  // SEND라는 이름에 함수를 만들었다 (매소드 = ) {   function SEND함수명 (index함수에 담겨지는 매게변수 / 있고 없고할수 있음. ) { 매게변수로 실행되는 로직기능 }    function 험수명 (){} 
  function SEND (index) {
    // 선택한 카드 인덱스 값을 selectedCard함수명에 넣어주고 selectedCard 참으로 표시한다.
    // cards[index].show = true
    // @엘로디샘 = 선택된 카드의 인덱스 값으로 카드 객체를 골라서 selectedCard 변수에 담고 
    var selectedCard = cards[index]
    // @엘로디샘 = selectedCard변수에 담겨진 객체의 show값을 true로 한다.
    selectedCard.show = true
    cards[index] = cards[index]; // 이건 왜 선언???????????????? @태오

    // 카드스 배열을 반복하면서 카드show가 true 인 카드만 변수에 담는다.  
    let selectedCards = [];

    for(let i = 0; i < cards.length ; i++) {
      if(cards[i].show === true) {
        selectedCards.push(cards[i])
      }
    }
    // 카드스 배열을 반복하면서 카드show가 true 인 카드만 변수에 담는다.  
    // const selectedCards = cards.filter(card => {
    //   return card.show === true
    // })

   
    // 변수에 담긴 값이 2일 경우 
    if(selectedCards.length === 2) {
      console.log(selectedCards[0].id === selectedCards[1].id)
      // 두개의 객체의 id(키) 값(true)이 같을 경우 
      if (selectedCards[0].id === selectedCards[1].id){
        // 
        for(let i = 0; i < cards.length ; i++) {
          if(cards[i].show === true) {
            cards[i].show = false;
            cards[i].done = true;
          }
        }
        //  cards.map(card => {
        //   if(card.show === true) {
        //     card.show = false;
        //     card.done = true;
        //   }
        // })

        cards = cards;

        // selectedCards[0].done = true
        // selectedCards[1].done = true
      } else {
        setTimeout(() => { 
          cards.map(card => {
          if(card.show) {
            card.show = false;
          }
        })
        cards = cards;
        }, 1000);
        
      }
      
      console.log(selectedCards);
    }
    // var selectedCard = cards[index]
    // selectedCard.show = true
  }
  </script>

<input type="checkbox" id="ck">
<label for="ck">카드 전체 보기</label>
<div class="pack wrap space-between gameStart">
  {#each cards as card ,index}
    <div class="card" 
    on:click="{() =>  SEND(index)}"
    class:open="{card.show === true|| card.done === true}"
    >
      <span class="layer">뒤</span>
      <span class="layer">{card.value}</span>
    </div>
  {/each}
</div>


<style lang="scss">
  .wrap{
    height:100vh;
    padding:50px;
    box-sizing:border-box;
    font-size:100px;
    background:rgb(224, 224, 224);
  }
  .card{
    position: relative;
    width:20%;height:250px;
    span{
      border-radius: 20px;
      transition: transform 1s ease-in-out .2s,  z-index 1s ease-in-out .2s; 
      &:nth-child(1){
        background:#e9ffcc;
        transform:rotateY(0);
        z-index: 10;
      }
      &:nth-child(2){
        background: rgb(255, 206, 206);
        transform: rotateY(180deg);
        z-index: 0;
      }
    }
    
  }
  // &:hover,
  .open,.selected{
      span:nth-child(1){
        transform:rotateY(180deg);
        z-index: 0;
      }
      span:nth-child(2){
        transform: rotateY(0);
        z-index: 10;
      } 
    }
 

  input:checked +label+ .gameStart {
    span:nth-child(1){
        transform:rotateY(180deg);
        z-index: 0;
      }
      span:nth-child(2){
        transform: rotateY(0);
        z-index: 10;
      } 
  }


  // 틀리면 wrong 넣었다가 빠지기 1초?
  .wrong {
	-webkit-animation: vibrate-1 0.3s linear infinite both;
	        animation: vibrate-1 0.3s linear infinite both;
  }
  @keyframes vibrate-1 {
    0% {
      transform: translate(0);
    }
    20% {
      transform: translate(-2px, 2px);
    }
    40% {
      transform: translate(-2px, -2px);
    }
    60% {
      transform: translate(2px, 2px);
    }
    80% {
      transform: translate(2px, -2px);
    }
    100% {
      transform: translate(0);
    }
  }

</style>