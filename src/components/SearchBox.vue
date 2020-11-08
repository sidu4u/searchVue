<template>
  <input type="text" :value="searchText" :oninput="updateSearchText"/>
</template>

<script>
export default {
  name: 'SearchList',
  props: {
   updateSearchText:Function,
   searchText:String
  }
}
</script>
