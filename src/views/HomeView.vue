<template>
  <input v-model.number="age" type="text" value="number" v-int/>
</template>

<script>
export default {
  data() {
    return {
     age: 0
    }
  },
  watch: {
    age(value) {
      if (value === '') {
        return
        }
          if (typeof value !== 'number') {
          throw new Error('invalid data type')
          }
          if (value < 1) {
          throw new Error('invalid age')
        }
      }
    }
  }
</script>