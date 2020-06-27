<template>
  <div v-on:click="storyClick" v-bind:class="selectedStatus">
    <img v-bind:src="require(`@/assets/${imgURL}`)">
    <p class='label'>{{label}}</p>
  </div>
</template>

<script>
import {EventBus} from "@/components/eventBus.js"

export default {
  name: 'Story',
  props: {
    setSocialMode: Function,
    info: {
      id: Number,
      isSelected: {
        type: Boolean,
        default: false
      },
      label: String,
      imgURL: String
    }
  },
  data() {
    return {
      selectedStatus: this.info.isSelected? 'selected': 'unselected',
      label: this.info.label,
      imgURL: this.info.imgURL,
    }
  },
  methods: {
    storyClick() {
      console.log("{STORY CLICKED")
      console.log(this.info.id==0)
      // EventBus.$off("update:socialMode")
      EventBus.$emit("update:socialMode", this.info.id==0)
    }
  }
};
</script>


<style scoped>
  .col-4 {
    text-align:center;
    margin:auto;
  }

  a {
    width: 100%;
  }

  img {
    width: 75px;
    height:75px;
    border: 2px solid #2a1e60;
    border-radius:50%;
    object-fit: cover;

  }

  .selected {
      border: 2px white solid;
      border-radius: 5px;
      padding-top: 20px;
      background-color: rgba(0, 0, 255, 0.20);
  }

  .unselected {
      padding-top: 22px;
  }

  .unselected:hover {
      border: 2px white solid;
      border-radius: 5px;
      padding-top: 20px;
  }
</style>
