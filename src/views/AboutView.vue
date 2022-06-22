<template>
  <ul v-if="response && response.items.length == 2">
    <li v-for="item in response.items" :key="item.item.id">
      {{ item.name }} {{ item.price }}
    </li>
  </ul>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      response: null
    }
  },
  mounted() {
    axios.get('http://localhost:3000/sample-api').then(res => {
      this.response = res.data
    })
  }
}
</script>