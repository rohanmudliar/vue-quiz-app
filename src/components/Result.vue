<template>
  <div class="result">
    <div class="title">{{ results[getIndex].title }}</div>
    <div class="desc">{{ results[getIndex].desc }}</div>
  </div>
</template>

<script>
export default {
  props: ["results", "correctAnswer"],
  computed: {
    getIndex() {
      let index = 0;
      this.results.forEach(({ min, max }, ind) => {
        if (this.correctAnswer >= min && this.correctAnswer <= max) index = ind;
      });

      return index;
    },
  },
};
</script>
