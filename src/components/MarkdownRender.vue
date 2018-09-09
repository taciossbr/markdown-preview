<template>
  <div 
    class=".render" 
    v-html="result"></div>
    <!-- <span> {{ msg }}</span> -->
</template>

<script>
import Remarkable from 'remarkable';

const md = new Remarkable();

export default {
    props: {
      markdown: String,
      // msg: String
    },
    computed: {
      result() {
        return md.render(this.markdown);
      }
    }
}
</script>

<style scoped>

</style>
