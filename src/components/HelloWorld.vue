<template>
  <div class="hello">
    <div v-for="(item, index) in itemRefs" :ref="setItemRef" :key="`ref_${index}`">item</div>
  </div>
</template>

<script>
// import  from 'vue'

export default {
  props: {
    title: {
      type: String,
      default: 'vue 3'
    },
    // TODO 
    age: {
      type: Number,
      default: 26
    }
  },
  setup(props) {
    console.log('props >> ', props.title)
    console.log('age >> ', props.age);
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
