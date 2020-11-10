<input type="checkbox" id="ck">
<label for="ck">카드 전체 보기</label>
<div class="pack wrap space-between gameStart">
  <div class="card">
    <span class="layer">뒤</span>
    <span class="layer">앞  🍇</span>
  </div>
  <div class="card">
    <span class="layer">뒤</span>
    <span class="layer">앞 🍋</span>
  </div>
  <div class="card">
    <span class="layer">뒤</span>
    <span class="layer">앞 🍉</span>
  </div>
  <div class="card">
    <span class="layer">뒤</span>
    <span class="layer">앞 🍍</span>
  </div>
</div>


<style lang="scss">
  .wrap{
    height:100vh;
    padding:50px;
    box-sizing:border-box;
    font-size:100px;
    background:#ccc;
  }
  .card{
    position: relative;
    width:20%;height:250px;
    margin:10px 0;
    border:1px solid #ccc;
    background:rgb(224, 224, 224);
    span{
      transition: transform 1s ease-in-out .2s,  z-index 1s ease-in-out .2s; 
    }
    span:nth-child(1){
      background:#e9ffcc;
      transform:rotateY(0);
      z-index: 10;
    }
   span:nth-child(2){
      background: rgb(255, 206, 206);
      transform: rotateY(180deg);
      z-index: 0;
    }
    &:hover{
      span:nth-child(1){
        transform:rotateY(180deg);
        z-index: 0;
      }
      span:nth-child(2){
        transform: rotateY(0);
        z-index: 10;
      } 
    }
  }

  // 시작하면 보여준다 
  // .gameStart{
  //   span:nth-child(1){
  //       transform:rotateY(180deg);
  //       z-index: 0;
  //     }
  //     span:nth-child(2){
  //       transform: rotateY(0);
  //       z-index: 10;
  //     } 
  // }

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
</style>