<template>
  <div class="searchList">
   <div v-if="!otherSearchPresent && !nameSearchPresent">   
   <h3>No Search Data Present</h3>
   </div>
   <div v-else>
        <SearchResult v-for="(item,i) in nameSearch" :key="i" :item="item"/>
        <div v-if="otherSearchPresent">
            <h3>
             {{`${searchText} found in items`}}
            </h3>
        </div>
        <SearchResult v-for="(item,i) in otherSearch" :key="i" :item="item"/>
   </div>
  </div>
</template>

<script>
import SearchResult from './SearchResult.vue';
import EmptySearch from './EmptySearch.vue';
export default {
  name: 'SearchList',
  components:{
      SearchResult
  },
  props: {
   searchText:String,   
   nameSearch:Array,
   otherSearch:Array
  },
  computed:{
      otherSearchPresent:function(){
          let test = this.otherSearch.length > 0;
          return test;
      },
      nameSearchPresent:function(){
          let test = this.nameSearch.length > 0;
          return test;
      }
  }
//   updated(){
//     console.log(this.searchResult.forEach(element => {
//         console.log('dad',element);
//     }));
//   }
}
</script>

<style scoped>
.searchList{
 height: 150px;
 overflow: auto;
 border: 1px solid grey ;
}
</style>