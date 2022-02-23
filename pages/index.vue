<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData() {
    const { data } = await axios.get(
      'https://marigotten.microcms.io/api/v1/blog',
      {
        headers: { 'X-MICROCMS-API-KEY': 'd68f8f45652e433dad584abc2e0e3b7f7573' }
      }
    )
    return data
  }
}
</script>
