<template>
  <div>
    <pre>
      {{ $store.state.user }}
    </pre>    
    <pre>
      {{ user }}
    </pre> 
  </div>
</template>

<script>
import { mapState } from 'vuex';

export default {
  name: 'IndexPage',

  mounted() {
    console.log(this.$name('Jon Snow'));
  },

  computed: {
    ...mapState({
      user: state => state.user
    })
  },
}
</script>
