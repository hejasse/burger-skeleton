
<template>
<div class="ingredient box">
    <label>
      <button v-on:click="incrementCounter">{{ counter }}</button>
      {{item["ingredient_"+ lang]}}, {{item.selling_price}}:-, {{item.stock}} pcs
    </label>
  </div>
<!-- </div> -->
<!-- </div> -->



</template>
<script>
export default {
  name: 'Ingredient',
  props: {
    item: Object,
    lang: String,
  },
    data: function () {
    return {
      counter: 0
    };
  },
  methods: {
    incrementCounter: function () {
      this.counter += 1;
      // sending 'increment' message to parent component or view so that it
      // can catch it with v-on:increment in the component declaration
      // (see ingredient html-tag in Ordering.vue)
      this.$emit('increment');
    },
    resetCounter: function () {
      this.counter = 0;
    }

  }
}

</script>
<style scoped>

</style>
