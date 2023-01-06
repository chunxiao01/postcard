<script setup>
import { nextTick, onMounted, ref } from "vue"
import AudioMusic from "@/assets/audio/Spring Festival.mp3"
const isAudioPlay = ref(false)
const audioplayer = ref(null)
const audioPlay = () => {
  isAudioPlay.value = !isAudioPlay.value
  if (audioplayer.value) {
    if (isAudioPlay.value) {
      audioplayer.value.play()
    } else {
      audioplayer.value.pause()
    }
  }
}
onMounted(() => {
  nextTick(() => {
    if (audioplayer.value) {
      if (isAudioPlay.value) {
        audioplayer.value.play()
      } else {
        audioplayer.value.pause()
      }
    }
  })
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
            <span>新年快樂</span>
          </div>
          <div class="happy-new-year-txt3"><span></span></div>
          <div class="happy-new-year-txt4"><span></span></div>
        </div>
        <div
          class="happy-new-year-audio"
          :class="{ 'audio-active': isAudioPlay }"
          @click="audioPlay"
        ></div>
        <div class="audioplayer" v-show="isAudioPlay">
          <audio ref="audioplayer" id="audioplayer" loop="loop" preload="auto">
            <source :src="AudioMusic" type="audio/mpeg" />
          </audio>
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
  background: linear-gradient(
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
  );
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
}

.happy-new-year-txt1,
.happy-new-year-txt2,
.happy-new-year-txt3,
.happy-new-year-txt4 {
  display: flex;
  flex: auto;
}

.happy-new-year-audio {
  position: fixed;
  width: 36px;
  height: 36px;
  border-radius: 50%;
  top: 20px;
  right: 20px;
  text-align: center;
  background: url("@/assets/img/audio.svg");
}
/* .icon {
  width: 100%;
  margin: auto;
  -webkit-animation: rotataZ 1.2s linear infinite;
  animation: rotataZ 1.2s linear infinite;
} */

.audio-active {
  -webkit-animation: rotataZ 1.2s linear infinite;
  animation: rotataZ 1.2s linear infinite;
}

@-webkit-keyframes rotataZ {
  0% {
    -webkit-transform: rotateZ(0deg);
  }
  100% {
    -webkit-transform: rotateZ(360deg);
  }
}
@keyframes rotataZ {
  0% {
    -webkit-transform: rotateZ(0deg);
  }
  100% {
    -webkit-transform: rotateZ(360deg);
  }
}
.audioplayer {
  position: absolute;
  z-index: -9999;
}
</style>
