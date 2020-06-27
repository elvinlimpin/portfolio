<template>
    <a v-bind:href="url"><button v-bind:class="this.buttonClass" v-bind:style="style">
        <i v-bind:class="icon"></i> <span v-if="this.isBigMode">{{ label }}</span>
    </button></a>
</template>

<script>
export default {
  name: 'SocialLink',
  props: {
      isBigMode: Boolean,
      info: {
        url: String,
        color: String,
        label: String,
        icon: String,
      }
  },
  data() {
    return {
        url: this.info.url,
        style: {
            backgroundColor: this.info.color
        },
        label: this.info.label,
        icon: this.info.icon.split(" "),
    }
  },
  computed: {
      buttonClass() {
          return ['btn', this.isBigMode? 'big':'smol']
      }
  }
};
</script>

<style scoped>
    .btn {
        background-color: grey;
        border-radius: 5px;
        color: white;
        font-weight: 400;
        letter-spacing: 0.1em;
        font-size: 1.3em;
    }

    .big {
        width: 100%;
        margin-bottom: 0.5em;
        display: block;
        padding: 1.2em;
    }

    .smol {
        display: inline;
        margin: 0.4em;
        padding: 0.5em 01em;
    }

    .btn:hover {
        background-color: transparent!important;
        color: white;
        border:  2px solid white;
        font-size: 1.4em;
    }
</style>