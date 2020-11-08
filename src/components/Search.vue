<template>
<div class="search">
<SearchBox :updateSearchText="updateSearchString" :searchText="searchText"/>
<div v-if="!dataNotPresent">
  <SearchList :nameSearch="nameSearch" :otherSearch="otherSearch" :searchText="searchText"/>
</div>
</div>
</template>

<script>
import SearchBox from "./SearchBox.vue";
import SearchList from "./SearchList.vue";

export default {
  name: 'Search',
  components: {
    SearchBox,
    SearchList
  },
  props: {
    searchData:Array
  },
  methods:{
    updateSearchString(event){
       this.searchText=event.target.value;
       this.updateSearchResult();
    },
    updateSearchResult(){
       if(!this.searchText){
         this.nameSearch=[];
         this.otherSearch=[];
         return;
       }
       this.nameSearch = this.customerData.filter(data => data.name.includes(this.searchText));
       this.otherSearch = this.customerData.filter(data => {
        let itemSearch = data.items.filter(item=>item.includes(this.searchText));
          console.log(data.name,itemSearch);
          return itemSearch.length>0;
       });
    }
  },
  computed:{
    dataNotPresent:function(){
      return this.nameSearch.length===0 && this.otherSearch.length===0  && !this.searchText;
    }
  },
  data() {
    return {
      searchText: '',
      customerData: this.searchData,
      nameSearch:[],
      otherSearch:[]
    }
  }
}
</script>

<style scoped>
.search{
  display: flex;
  flex-direction: column;
  width: 200px;
}
</style>