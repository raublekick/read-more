<template>
	<div>
		<p>
      <span v-html="formattedString"></span>
      <span v-show="text.length > maxChars">
        <div :class="{ inline: inline }">
          <slot name="links">
            <a :class="align" :href="link" id="readmore" v-show="!internalReadMore" v-on:click="triggerReadMore($event, true)">{{moreStr}}</a>
            <a :class="align" :href="link" id="readmore" v-show="internalReadMore" v-on:click="triggerReadMore($event, false)">{{lessStr}}</a>
          </slot>
        </div>
      </span>
    </p>
    
    <div class="clearfix"/>
	</div>
</template>

<script>
export default {
  props: {
    moreStr: {
      type: String,
      default: "Read more"
    },
    lessStr: {
      type: String,
      default: "Read less"
    },
    text: {
      type: String,
      required: true
    },
    link: {
      type: String,
      default: "#"
    },
    maxChars: {
      type: Number,
      default: 100
    },
    align: {
      type: String,
      default: "left"
    },
    inline: {
      type:Boolean,
      default: false
    },
    value: {
      type: Boolean,
      default: false
    }
  },

  data() {
    return {
      internalReadMore: true
    };
  },

  computed: {
    formattedString() {
      var val_container = this.text;

      if (!this.internalReadMore && this.text.length > this.maxChars) {
        val_container = val_container.substring(0, this.maxChars) + "...";
      }

      return val_container;
    }
  },

  methods: {
    triggerReadMore(e, b) {
      if (this.link == "#") {
        e.preventDefault();
      }
      if (this.lessStr !== null || this.lessStr !== "") this.internalReadMore = b;
    }
  },

  watch: {
    value: function(val) {
      this.internalReadMore = val;
    }
  },

  created() {
    this.internalReadMore = this.value;
  }
};
</script>

<style scoped>
.left {
}
.right {
  float: right;
}
.clearfix {
  overflow: auto;
}
.inline {
  display:inline;
}
</style>
