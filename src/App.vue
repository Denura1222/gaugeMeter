<script setup>
import { ref,computed } from 'vue'



let increaseValue =ref(0);




const indication = (number) => {

  console.log("oudhwudn",number)


  if (number > 100 || number < 0) {
    increaseValue.value =0;
    return 0
    
  }

  const returnedValiue = increaseValue.value / 100 / 2
  return returnedValiue
}


</script>

<template>
  <main id="container">
    <div id="main">
      <div id="mainBox" />
      <div id="arrow" :style="{ transform: `rotate(${indication(increaseValue.valueOf())}turn)` }">
        <div id="arrowHead" />
        <div id="arrowBody" />
      </div>

      <div id="subBox" />
      <div id="text">
        <span id="text" v-if="increaseValue.valueOf() > 100">0</span>
        <span id="text" v-else>{{ increaseValue.valueOf() }}</span>
      </div>
      <div id="indicationOne">0</div>
      <div id="indicationTwo">50.00</div>
      <div id="indicationThree">100.00</div>
    </div>

    <div>
      <button @click="increaseValue++" id="button">
        increase
      </button>
    
    </div>
  </main>
</template>

<style scoped>
#container {
  width: 100%;
  max-width: 200vw;}

#main {
  padding: 50px;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  justify-items: center;
  background-color: white;
  overflow: hidden;
}
#mainBox {
  width: 20rem;
  height: 10rem;
  background: rgb(225, 202, 70);
  background: linear-gradient(
    90deg,
    rgba(225, 202, 70, 1) 0%,
    rgba(117, 201, 82, 1) 35%,
    rgba(70, 158, 213, 1) 100%
  );
  border-radius: 10rem 10rem 0 0;
  position: relative;
}
#arrow {
  transform-origin: bottom center;
  z-index: 70;
  display: flex;
}

#arrowHead {
  width: 0;
  height: 0px;
  border-right: 30px solid black;
  border-top: 5px solid transparent;
  border-bottom: 5px solid transparent;
  position: absolute;
  z-index: 90;
  right: 120px;
}
#arrowBody {
  height: 10px;
  width: 130px;
  background-color: rgb(255, 255, 255);
  position: absolute;
  z-index: 80;
  right: -10px;
}
#subBox {
  width: 16rem;
  height: 8rem;
  background-color: rgb(255, 255, 255);
  border-radius: 10rem 10rem 0 0;
  position: absolute;
  z-index: 60;
  transform: translateY(13%)

}

#text {
  font-size: 50px;
  font-weight: bolder;
  position: absolute;
  z-index: 80;
  margin-right: 40px;
}
#indicationOne {
  font-size: 20px;
  font-weight: bolder;
  position: absolute;
  z-index: 80;
  transform: translate(-200px,70px);

}
#indicationTwo {
  font-size: 20px;
  font-weight: bolder;
  position: absolute;
  z-index: 80;
  transform: translate(0px,-100px);


}
#indicationThree {
  font-size: 20px;
  font-weight: bolder;
  position: absolute;
  z-index: 80;
  transform: translate(200px,70px);



}
#button{
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  transform: translate(750px,0px);

  
}
button:hover {
  opacity: 90%;
  transition: all;
  cursor: pointer;
  position: absolute;

}
</style>
