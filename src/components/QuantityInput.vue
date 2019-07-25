<template>
  <div>
      <p>Quantity:</p>
      <select  @change="selectChange">
        <option v-for="item in getRange()" :value="item" v-bind:key="item" :selected="item == value">{{ item }}</option>
      </select>
      <p><input v-show="this.current === selectMax + '+'" @keyup="inputChange"></p>
	</div>
</template>


<script>
export default {
  name: 'QuantityInput',
  props: {
    value: Number,
    selectMin: Number,
    selectMax: Number
  },
  data() {
    return {
        current: undefined
    }
  },
    methods:{      
    selectChange(event) {
      this.current = event.target.value;
      this.$emit('select-change', event.target.value);
    },
    inputChange(event) {
      this.$emit('select-change', event.target.value);
    },
    getRange: function () {    
      var foo = [];
      for (var i = this.selectMin; i <= this.selectMax; i++) {
        foo.push(i);      
      }
      foo.push(this.selectMax + '+');

      return foo;
    }
  }
  
}
</script>