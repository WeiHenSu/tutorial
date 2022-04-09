<script>

export default ({
  data() {
    return{
      isawe:true,
      message:''
    }
  },
  methods:{
    awe(){
      this.isawe = !this.isawe
    }
  }
})
</script>


<template>
  <button @click="awe">click me plz</button>
  <h1 v-if="isawe">Vue is awesome</h1>
  <h1 v-else>no!!</h1>
</template>