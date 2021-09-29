<template>
  <div class="home">
    home 
    <Homehead></Homehead>
  </div>
</template>

<script>
// @ is an alias to /src
import Homehead from '@/pages/home/Homehead'

export default {
  name: 'Home',
  components: {
    Homehead
  }
}
</script>
