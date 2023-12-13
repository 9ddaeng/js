<template>
<div>
  <p class="guide">숫자를 입력해주세요.</p>
  <div>
    <p v-if="this.count == 1"> 도전 횟수 : {{ this.count }}</p>
  </div>
  <div>
    <input type="text" id="num" @keydown.enter="shot"/>
  </div>
  <div>
    <button type="button" id="shot" @click="shot"> 입력하기 </button>
  </div>
  <div class="notice">
    <p>strike : {{ this.strike }}</p>
    <p>ball : {{ this.ball }}</p>
  </div>
</div>

</template>

<script>
export default({
  name: "game",
  mounted() {
    this.answer = parseInt(Math.random()*10000);
  },
  data() {
    return {
      count: 0,
      answer: "",
      strike: 0,
      ball: 0,
      number: '',
    }
  },
  methods: {
    shot() {
      console.log("answer first="+this.answer);     
      this.number = document.querySelector('#num').value;

      // 유효성 검사
      if((this.number.length > 4) || (this.number.length < 4)) {
        alert('네 자리의 숫자를 입력해주세요.');
        document.querySelector('#num').value = '';
      } else {
        this.count +=1;
      }

      

    },

  }
})
</script>

<style>
.guide {
  font-size: 25px;
  font-weight: bold;
}

#num {
  width: 300px;
  height: 60px;
  font-size: 30px;
  text-align: center;
}

#shot {
  width: 80px;
  height: 30px;
  font-size: 18px;
  margin-top: 20px;
}

.notice > p {
  font-size: 20px;
  font-weight: bold;
}

.notice {
  margin-top: 5%;
}
</style>