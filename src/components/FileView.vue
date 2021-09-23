<template>
<div class="file-icons">
<span class="material-icons">source</span>
  <p class="file">{{name}}</p>
</div>
</template>

<script>
export default {
  name: 'FileView',
  props: {
    name: String
  }
}
</script>

<style scoped lang="scss">
.file{
  color: green;
  text-align: center;
  word-wrap: break-word;
  margin: 0;
}
.file-icons {
  cursor: pointer;
  &:focus,
        &:active,
        &:hover {
            background: #35c0fc;
            opacity: 0.9;
        }
}
.file-icons {
  > span {
    color: green;
    font-size: 6vw;
    display: block;
  }
}



</style>
