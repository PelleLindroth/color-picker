<template>
  <ul>
    <li v-for="color in getMatch" :key="color" @click="$emit('click', color)">
      {{ color }}
    </li>
  </ul>
</template>

<script>
export default {
  props: ["match"],
  computed: {
    getMatch() {
      return this.$store.getters.matchColor(this.match);
    },
  },
  // data(){ return {
  //   colors: ['red','green','blue'] // Change this to a vuex getter that filters based on this.match
  // }},
};
</script>

<style scoped lang="scss">
ul {
  position: absolute;
}
</style>
