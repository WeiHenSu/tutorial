<script>
export default ({
  data() {
    return{
      count:0
    }
  },
  methods:{
    countclick(){
      this.count++
    }
  }
})
</script>


<template>
  <button @click="countclick">click me {{count}}</button>
</template>