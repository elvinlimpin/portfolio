<template>
  <div class="row">
      <a v-bind:href="url">
          <button class="btn featured">
              Featured Link:
              <span class="underline">
                  {{label}}
              </span>
          </button>
      </a>
      <!-- <p>I'm a BSc Computer Science student and software developer interested in design, development, and the tech world. I look forward to helping turn ideas into the next big thing.</p> -->
  </div>
</template>

<script>
export default {
  name: 'FeaturedRow',
  data() {
    return {
      label: "Post Secondary Survey",
      url: "https://docs.google.com/forms/d/e/1FAIpQLSc9MMgqfwwd0hAfic37Z3WuYk_iPYTLaewb8Jjyi-JSltcTwg/viewform?usp=send_form",
    }
  }
};
</script>

<style scoped>
  .row {
    margin-top:1em;
  }
  a {
    margin: auto;
  }

  .btn.featured {
    background-color: white;
    color: black;
    border:  2px solid white;
    font-size: 1.2em;
    padding-left:2em;
    padding-right:2em;
  }

  .btn.featured:hover {
    font-size: 1.2em;
    background-color: transparent;
    color: white;
  }

</style>
