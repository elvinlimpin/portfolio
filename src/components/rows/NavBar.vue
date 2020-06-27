<template>
  <div class="row">
    <div class="col-4" v-bind:key="story.id" v-for="story in stories">
      <a href="#">
        <Story v-bind:info="story" />
      </a>
    </div>
  </div>
</template>

<script>
import Story from '@/components/repeaters/Story';


export default {
  name: 'NavBar',
  components: {
    Story
  },
  data() {
    return {
      stories: [
        {
          id: 0,
          label: "Social Links",
          imgURL: "social.png",
          isSelected: true,
        },
        {
          id: 1,
          label: "CV / Portfolio",
          imgURL: "work.png",
          isSelected: false,
        },
        {
          id: 2,
          label: "Cool Things",
          imgURL: "fun.png",
          isSelected: false,
        },
      ]
    }
  }
}
</script>

<style scoped>
</style>
