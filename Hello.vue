
<script>
export default ({
  data(){
    return{
      message:'Hello world'
    }
  },
})
</script>

<template>
  {{message}}
  {{message.split('').reverse().join('')}}
</template>

