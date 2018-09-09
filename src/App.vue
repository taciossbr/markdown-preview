<template>
  <div id="app">
    <div class="">
      <!-- <div class="text-center"> -->
        <h1 class="light text-center">Markdown Preview</h1>
      <!-- </div> -->
    </div>
    <div class="row">
      <div class="col col-6">
        <h4 class="text-center light">Markdown</h4>
        <textarea 
          v-model="markdown"
          class="info"
        />
      </div>
      <div class="col col-6">
        <h4 class="text-center light">Preview</h4>
        <!-- <div 
          class="info" 
          v-html="result"></div> -->
        <render v-bind:markdown="markdown" msg="teste"/>
      </div>
    </div>
  </div>
</template>

<script>

import Remarkable from 'remarkable';
import render from './components/MarkdownRender';

const md = new Remarkable();

export default {
  name: 'app',
  data () {
    return {
      markdown: '',
    }
  },
  computed : {
    result() {;
      return md.render(this.markdown);
    }
  },
  components: {
    render
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin: 0 auto;
  margin-top: 60px;
  width: 100%;
  max-width: 900px;
}

h1, h2 {
  font-weight: normal;
}

a {
  color: #42b983;
}

.text-center {
  text-align: center;
}

.container {
  display: flex;
}
.col {
  display: flex;
  flex-direction: column;
}
.row {
  display: flex;
  flex-direction: row;
  justify-content: center;
  justify-content: space-between;
}
.col-6 {
  width: 48%;
}
textarea {
  resize: none;
  width: 100%;
  min-height: 400px;
}

</style>
