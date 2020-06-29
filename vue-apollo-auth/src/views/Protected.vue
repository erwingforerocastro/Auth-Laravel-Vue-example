<template>
  <div>
    <h2>Información del usuario</h2>
    <div v-if="me">
      <div>{{ me.id }}</div>
      <div>{{ me.name }}</div>
      <div>{{ me.email }}</div>
    </div>
  </div>
</template>

<script>
import gql from 'graphql-tag'

export default {
  data() {
    return {
      me: null
    }
  },
  apollo: {
    me: gql`query {
      me {
        id
        name
        email
      }
    }
    `
  }
}
</script>

