<template>
  <div class="hello">
    <div v-for="(item, index) in itemRefs" :ref="setItemRef" :key="`ref_${index}`">item</div>
  </div>
</template>

<script>
/* eslint-disable */
import { reactive, readonly, toRefs } from 'vue'

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
    const { title } = toRefs(props)
    console.log('props >> ', props.title)
    console.log('props toRefs >>', title.value)
    console.log('age >> ', props.age)


    let count = reactive({
      cnt: 0
    })
    let copy = readonly(count)
    count.cnt++
    copy.cnt++
    console.log('reactive >>', count)
    console.log('readonly >>', copy)

  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
