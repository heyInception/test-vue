<template>
  <FolderView name="$main" :folders="folders" :files="files" />
</template>

<script>
import FolderView from './components/FolderView.vue'
import data from './data/list';

export default {
  name: 'App',
  components: {
    FolderView
  },
  data: () => data
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 968px;
  margin: auto;
  background-color: #fff;
  padding: 25px;
  border: 1px solid #000;
  border-radius: 25px;
}
body {
  background: -webkit-linear-gradient(45deg, rgb(197, 64, 229), rgb(45, 90, 199));
  background: -moz-linear-gradient(45deg, rgb(197, 64, 229), rgb(45, 90, 199));
  background: linear-gradient(45deg, rgb(197, 64, 229), rgb(45, 90, 199));
  background-repeat: no-repeat;
  height: 100vh;
}
#app {
  > .folder-files {
    border: 1px solid #ccc;
  }
}
</style>
