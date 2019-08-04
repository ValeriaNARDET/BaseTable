<template>
  <div class="container">
    <nuxt-link tag='button' class='back-btn' to='/'>Go back</nuxt-link>
    <baseTable
      v-if="comments"
      :content='getComments'
    />
  </div>
</template>

<script>
import BaseTable from '~/components/Base-Table.vue'

export default {
  async asyncData() {
    const response = await fetch('https://jsonplaceholder.typicode.com/comments')
    const comments = await response.json()
    return {comments}
  },
  data: () => ({
    comments: [],
  }),
  components: {
    BaseTable,
  },
  computed: {
    getComments() {
      let tableContent = []
      this.comments.map(i => {
        tableContent.push({
          Id: i.id,
          Name: i.name,
          Email: i.email,
          Message: i.body,
        })
      })
      return tableContent
    }
  }
}
</script>

<style>