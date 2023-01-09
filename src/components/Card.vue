<script setup>
import { onMounted, ref, reactive } from "vue"
const words = reactive([
  "新年快樂",
  "兔個吉祥",
  "錢兔似錦",
  "大展宏兔",
  "好事成兔",
  "兔故納新",
  "前兔無量",
  "兔年大吉"
])
const word = ref("新年快樂")
const flag = ref(1)
onMounted(() => {
  setInterval(() => {
    if (flag.value < words.length) {
      word.value = words[flag.value]
      flag.value++
    } else {
      flag.value = 0
    }
  }, 5168)
})
</script>
<template>
  <div class="card">
    <div class="happy-new-year">
      <div class="happy-new-year-content">
        <div class="happy-new-year-text">
          <div class="happy-new-year-txt1"><span></span></div>
          <div class="happy-new-year-txt2"><span></span></div>
          <div class="happy-new-year-txt">
            <span>{{ word }}</span>
          </div>
          <div class="happy-new-year-txt3"><span></span></div>
          <div class="happy-new-year-txt4"><span></span></div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  width: 100%;
  height: 100vh;
}
.happy-new-year {
  width: 100%;
  height: 100%;
}

.happy-new-year-content {
  position: relative;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0);
  /*background: linear-gradient(
    to bottom,
    #e12020,
    #dd211f,
    #d01f1f,
    #c21f20,
    #b61e20,
    #ab1d22,
    #9e1d24,
    #981d24,
    #8d1c23,
   #8b1d25
  );*/
  /* background: url("@/assets/img/bg.png") no-repeat;
  background-position: center;
  background-size: 100% 100%; */
}

.happy-new-year-text {
  display: flex;
  width: 100%;
  height: 100%;
}

.happy-new-year-txt {
  display: flex;
  width: 60px;
  height: 100%;
}

.happy-new-year-txt span {
  display: flex;
  align-self: center;
  width: 100%;
  line-height: 80px;
  word-wrap: break-word;
  text-align: center;
  color: #ffd8b3; /*#ffd700 #cd9694*/
  font-size: 50px;
  font-weight: 600;
  margin-bottom: 100px;
  transition: all 2.023s;
}

@keyframes wordAnimaition {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.happy-new-year-txt1,
.happy-new-year-txt2,
.happy-new-year-txt3,
.happy-new-year-txt4 {
  display: flex;
  flex: auto;
}
</style>
