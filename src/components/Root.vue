<template>
  <my-nav></my-nav>
</template>
<script>
import Home from './Home'
import Navbar from './Shared/Navbar'
export default {
  name: 'Root',
  components : {
    'my-nav': Navbar,
    'my-home': Home
  }
  
}
</script>

