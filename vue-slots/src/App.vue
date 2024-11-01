<template>

  <!-- <SlotComp>
    <h4>我来自父组件</h4>
    <div>
      <p>slot</p>
      <p>slot2</p>

    </div>

  </SlotComp> -->
  <!-- <SlotComp2>
    <template v-slot:footer>
      <p>我是footer插槽内容</p>
    </template>
<template #header>
      <p>我是header插槽内容：{{ msg }}</p>
    </template>
</SlotComp2> -->

  <!-- 使用作用域插槽 -->
  <!-- <SlotComp3 v-slot="slotProps">
    <p>我是父组件本身的数据：{{ msg }}</p>
    <p>父组件传递子组件的数据：{{ slotProps.childMsg }}</p>
  </SlotComp3> -->

  <!-- 使用具名插槽 -->
  <SlotComp3>
    <template #header="slotProps">
      <p>{{ msg }}-{{ slotProps.childMsg }}</p>
    </template>
  </SlotComp3>


</template>


<script>
import SlotComp from "./components/SlotComp.vue";
import SlotComp2 from "./components/SlotComp2.vue";
import SlotComp3 from "./components/SlotComp3.vue";

export default {
  components: {
    SlotComp,
    SlotComp2,
    SlotComp3,
  },
  data() {
    return {
      msg: "我来自父组件"
    }
  }
}

</script>