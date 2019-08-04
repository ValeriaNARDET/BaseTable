<template>
  <div class="container">
    <nuxt-link tag='button' class='back-btn' to='/'>Go back</nuxt-link>
    <baseTable
      v-if="users"
      :content='getUsers'
      :bigTable='true'
    />
  </div>
</template>

<script>
import BaseTable from '~/components/Base-Table.vue'

export default {
  async asyncData() {
    const response = await fetch('https://jsonplaceholder.typicode.com/users')
    const users = await response.json()
    return {users}
  },
  data: () => ({
    users: [],
  }),
  components: {
    BaseTable,
  },
  computed: {
    getUsers() {
      let tableContent = []
      this.users.map(i => {
        tableContent.push({
          Id: i.id,
          Nickname: i.username,
          City: i.address.city,
          Company: i.company.name,
        })
      })
      return tableContent
    }
  }
}
</script>

<style>