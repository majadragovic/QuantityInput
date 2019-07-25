<template>
  <div id="app">
    <QuantityInput :value="5" :selectMin="2" :selectMax="10" @select-change="onClickChild"/>
  </div>
</template>

<script>
import QuantityInput from './components/QuantityInput.vue'

export default {
  name: 'app',
  components: {
    QuantityInput
  },
  methods: {
    onClickChild (value) {
      console.log(value);
    }
   }
}
</script>
