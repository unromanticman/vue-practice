<template>
<ul>
  <li v-for="item in list" v-bind:key="item" >
    <a
      :href="item.url"
      target="_blank"
    >
    {{ item.name }}
    </a>
  </li>
</ul>
</template>
<script>
export default {
  props: {
    // attribute name: Type
    list: Array
  }
};
</script>
<style>
ul {
  list-style-type: none;
  padding: 0;
}
a {
  color: #42b983;
}
li {
  display: inline-block;
  margin: 0 10px;
}
</style>
