
<template>
    <ul class="nav justify-content-center">
  <li class="nav-item">
    <RouterLink class="nav-link" to="/">Home</RouterLink>
  </li>
  <li class="nav-item">
    <RouterLink class="nav-link" to="/add">add</RouterLink>
  </li>
  <li class="nav-item">
    <RouterLink to="/Update" class="nav-link">update</RouterLink>
  </li>
  <li class="nav-item">
    <RouterLink class="nav-link" to="/Delete">delete</RouterLink>
  </li>
</ul>
</template>
<script>
export default{
name:"Navbar",
};
import  {RouterLink,RouterView} from 'vue-router'

</script>