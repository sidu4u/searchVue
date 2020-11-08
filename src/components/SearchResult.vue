<template>
  <div class="searchResult">
    <div>{{id}}</div>
    <div>{{name}}</div>
    <div>{{restData}}</div>
  </div>
</template>

<script>

export default {
  name: 'SearchResult',
  props: {
   item:Object
  },
  data(){
      let {id,name,address,items} = this.item;
      return {
          id,
          name,
          restData : address + items.join(',')
      }
  }
}
</script>

<style scoped>
.searchResult{
    display: flex;
    flex-direction: column;
    border-bottom: 1px solid grey;
}
.searchResult:hover{
     background-color: yellow;
    opacity: 0.3;
    cursor: pointer;
}
</style>
