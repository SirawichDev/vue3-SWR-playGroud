<template>
  <div class="hello">
    <button @click="inc">Count is: {{ count }}, double is , click to increment.</button>
  </div>
</template>

<script>
import { ref, computed, onMounted } from "vue";
export default {
  setup() {
    console.log("vvv");
    let count = ref(1);
    const double = computed(() => {
      console.log("o");
      return count.value * 2;
    });
    function inc() {
      return count.value++;
    }
    onMounted(() => console.log("ff")); // เป็นตอนหลัง setup -> mounted

    return {
      count,
      double,
      inc,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
