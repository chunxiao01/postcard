<script setup></script>
<template>
  <div class="card">
    <div class="happy-new-year">
      <div class="happy-new-year-content">
        <div class="happy-new-year-text">新年好！</div>
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
  background: url("@/assets/img/bg.png") no-repeat;
  background-position: center;
  background-size: 100% 100%;
}

.happy-new-year-text {
  color: #cd9694; /*#ffd700*/
  font-size: 30px;
}
</style>
