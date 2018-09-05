<template>
  <div id="app">
    <VmEditor width="950px" 
              height="400px" 
              @upload="showHtml">
    </VmEditor>
    <div>{{previewHtml}}</div>
  </div>
</template>

<script>
import VmEditor from './components/vm-editor.vue'
// import VmEditor from '../dist/vm-editor.min.js'
export default {
  name: 'app',
  components: {
    VmEditor
  },
  data: function () {
    return {
      previewHtml: ''
    }
  },
  methods: {
    showHtml: function (data) {
      this.previewHtml = data
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 30px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.preview{
  margin-top: 30px;
  width: 950px;
}
.author{
  margin-top: 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
p.desc{
  margin-bottom: 40px;
}
h2 {
  font-weight: bold;
  margin-bottom: 0;
}

ul {
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
  text-decoration: none;
}
</style>
