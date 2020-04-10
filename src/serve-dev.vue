<script>
import Vue from 'vue';
import VueReadMore from '@/vue-read-more.vue';

export default Vue.extend({
  name: 'ServeDev',
  data() {
    return {
      toggle: true,
      text: "<strong>Sed ut perspiciatis</strong> unde omnis iste natus error sit voluptatem <i>accusantium doloremque laudantium</i>, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatur, vel illum qui dolorem eum fugiat quo voluptas nulla pariatur?"
    }
  },
  components: {
    VueReadMore
  }
});
</script>

<template>
  <div id="app">
    <vue-read-more :text="text" />

    <vue-read-more :text="text" align="right" />
    
    <vue-read-more :text="text" />

    <vue-read-more :text="text" inline />

    <vue-read-more :text="text" lessStr="" />

    <vue-read-more :text="text" lessStr="read less" v-model="toggle">
      <template slot="links">
        <button v-on:click="toggle = !toggle">Toggle</button>
      </template>
    </vue-read-more>
  </div>
</template>
