<template>
  <Search :searchData="customers"/>
</template>

<script>
import Search from './components/Search.vue';

export default {
  name: 'App',
  components: {
    Search
  },
  data(){
    return {customers:[
      {id:'122',
       name:'Siddharth',
       address:'qweqw',
       items:[
         'pizza cheesy',
         'burger veg',
         'roti tandoori',
         'doll plastic'
       ],
       pincode:'23232323'
      },
      {
        id:'111',
        name:'Praveen',
         items:[
         'table imported',
         'shoes nike',
         'coat fur',
         'tie dotted'
       ],
        address:'ewcawda',
        pincode:'34355435'
      },
       {id:'156',
       name:'Mohit',
        items:[
         'bed iron',
         'cat white',
         'sofa wood',
         'wine red'
       ],
       address:'qweqw',
       pincode:'23232323'
      },
      {
        id:'102',
        name:'Rachit',
         items:[
         'dance floor',
         'window paint',
         'cutting blade',
         'empty glass'
       ],
        address:'ewcawda',
        pincode:'34355435'
      }
    ]
    }
  }
}
</script>
