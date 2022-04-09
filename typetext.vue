<script>

export default ({
  data() {
    return{
      text:''

    }
  },
})
</script>


<template>
  <input v-model="text" placeholder="type here">
  {{text}}
</template>
