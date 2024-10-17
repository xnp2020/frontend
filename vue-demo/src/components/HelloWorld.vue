<template>
  <div :id="dynamicId" :class="dynamicClass" :title="dynamicTitle">测试</div>
  <button :disabled="isButtondisabled">动态标题</button>
  <div v-bind="objectOfAttrs">测试2</div>
</template>

<script >
export default {
  data() {
    return {
      dynamicClass: 'appclass',
      dynamicId: 'appid',
      dynamicTitle: null,
      isButtondisabled: true,
      objectOfAttrs:{
        class: 'appclass',
        id: 'appid',
      }
    }
  }
}
</script>

<style>
.appclass{
  color: #f00;
  font-size: 30px;
}

</style>

