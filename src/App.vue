<template>
  <div id="app">
        <!-- header desc-->
    <div class="container-fluid">
        <HeaderRow />
        <FeaturedRow />
        <br>
        <NavBar />
        <SocialLinks />
    </div>
    <br>
    <p class='smol'>Copyright &copy; 2020 Elvin Limpin 2020. All rights reserved. </p>
  </div>
</template>

<script>
import HeaderRow from '@/components/rows/HeaderRow';
import FeaturedRow from '@/components/rows/FeaturedRow';
import NavBar from '@/components/rows/NavBar';
import SocialLinks from '@/components/content/SocialLinks';

export default {
  name: 'App',
  components: {
      HeaderRow,
      FeaturedRow,
      NavBar,
      SocialLinks
  },
  data() {
    return {
      background: {
          color0: "#694ff6",
          color1: "#f09cab",
      },
      font: 'Lato',
    }
  },
  mounted() {
      const bodyStyle = document.body.style;
        bodyStyle.backgroundColor = this.background.color0;
        bodyStyle.backgroundImage = `linear-gradient(${this.background.color0},${this.background.color1})`;

      const appStyle = document.getElementById('app').style;
        appStyle.fontFamily = `${this.font}, sans-serif`;
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,300,0,400;0,700;0,900;1,400;1,700;1,900&display=swap');

body {
    min-height: 100vh;
}

#app {
    width: 95%;
    max-width: 700px;
    margin: auto;
    text-align: center;
    color: #f0f0f0;
}

div {
    display: block;
}

h2, h2, h4, h2, h6 {
    font-weight: bold;
}

h4 {
    font-weight: lighter;
    text-align: left;
}

a, a:hover, a:visited, a:active {
    color: inherit;
    text-decoration: inherit;
}

.label {
    font-size: 1em;
    margin-top: 0.4em;
    font-weight: 400;
    letter-spacing: 0.1em;
}

.container, .container-fluid {
    margin-left: auto;
    margin-right: auto;
    padding-right: 15px;
    padding-left: 15px;
    position: relative;
}
.smol {
    font-size: 0.75em;
}
</style>
