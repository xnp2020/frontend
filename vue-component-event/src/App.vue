<template>
  <!-- <componentEvent /> -->
  <!-- <Main /> -->
  <!-- <CompA /> -->
  <AttrComponents class="test" />
</template>

<script>

import ComponentEvent from './components/ComponentEvent.vue'
import Main from './components/Main.vue'
import CompA from './components/CompA.vue'
import AttrComponents from './components/AttrComponents.vue'

export default {
  components: {
    ComponentEvent,
    Main,
    CompA,
    AttrComponents
  }
}

</script>