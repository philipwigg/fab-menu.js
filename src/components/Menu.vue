<template>
<table id="menu-items">
  <tr>
    <th>Name</th>
    <th>Details</th>
  <tr v-for="item in menuItems" :key="item.name">
    <td>{{ item.name }}</td>
    <td>{{ item.details }}</td>
  </tr>
</table>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      menuItems: null
    }
  },
  mounted () {
    axios
      .get('https://dev.menu.ninja/api/menu/156?key=8j5vfe%24*pfb**rzt&pretty=1')
      .then(response => (this.menuItems = response.data.menu.items))
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
