<template>
    <div style="margin-top:1em">
        <span v-bind:key="link.id" v-for="link in links">
            <SocialLink v-bind:isBigMode="isBigMode" v-bind:info="link" />
        </span>
    </div>
</template>

<script>
import SocialLink from '@/components/repeaters/SocialLink';
import {EventBus} from "@/components/eventBus.js";

export default {
  name: 'SocialLinks',
  components: {
    SocialLink
  },
  data() {
    return {
      isBigMode: true,
      links: [
        {
            id: 0,
            url: "https://www.youtube.com/c/ElvinLimpin",
            color: "#C52F30",
            label: "Youtube",
            icon: "fab fa-youtube",
        },
        {
            id: 1,
            url: "https://www.instagram.com/elvinlimpin/",
            color: "#C52F30",
            label: "Instagram",
            icon: "fab fa-instagram",
        },
        {
            id: 2,
            url: "https://www.linkedin.com/in/elvinlimpin/",
            color: "#0085AE",
            label: "LinkedIn",
            icon: "fab fa-linkedin",
        },
        {
            id: 3,
            url: "https://github.com/elvinlimpin/",
            color: "#767676",
            label: "GitHub",
            icon: "fab fa-github",
        },
        {
            id: 4,
            url: "https://www.freecodecamp.org/elvinlimpin/",
            color: "#0A0A23",
            label: "freeCodeCamp",
            icon: "fab fa-free-code-camp",
        },
        {
            id: 5,
            url: "https://codepen.io/elvinlimpin/",
            color: '#47Cf73',
            label: "codepen",
            icon: "fab fa-codepen",
        },
      ]
    }
  },
  mounted() {
      EventBus.$on("update:socialMode", msg => {
          this.isBigMode = msg
      })
  }
};
</script>

<style scoped>

</style>