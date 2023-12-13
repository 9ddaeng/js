<template>
<div>
  <h1><p>*숫자야구*</p></h1>
<div class="rules">
  <p>1. 네 자리의 숫자를 입력한다.</p>
  <p>2. 자리는 틀렸지만 숫자는 맞을 경우, 1ball!</p>
  <p>3. 자리와 숫자 모두 맞을 경우, 1strike~</p>
  <p>4. 모두 틀렸을 경우 out!!!</p>
  <p id="caution">!!!도전 기회는 총 10번!!!</p>
</div>
<div>
<button id="start" @click="$router.push('/game')"> 도전하기 </button>
</div>
</div>
</template>

<script>
export default({
  name: 'baseball',
})

</script>

<style>

.rules > p {
  font-size: 18px;
  color: black;
}

#caution {
  color: red;
  font-weight: bold;
  margin-top: 3%;
}

#start {
  width: 100px;
  height: 40px;
  font-weight: bold;
  font-size: 20px;
}
</style>