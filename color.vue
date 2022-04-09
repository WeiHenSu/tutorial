
<script>
export default ({
  data(){
    return{
      titleclass: 'title'
    }
  }
})
</script>

<template>
    <h1 :class='titleclass'>Make me red</h1>
</template>


<style>
.title{
  color:red
}
</style>
