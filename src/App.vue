

<template>
  <Navbar/>
  <RouterView />
</template>


<script>
export default{
  name:"App",
  components: {
    Navbar
  },
  


}


import Navbar from './components/Navbar.vue';
import  {RouterLink,RouterView} from 'vue-router'

</script>