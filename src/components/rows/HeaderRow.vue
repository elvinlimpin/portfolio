<template>
  <div class="row"> 
    <div class="col-sm-1"></div>

    <div class='col-sm-4'>
      <div class="img-container">
        <img v-bind:src="require(`@/assets/${imgURL}`)" />
      </div>
    </div>
    
    <div class="col-sm-6">
      <br>
      <h2> {{ name }}</h2>
      <p>{{description}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FeaturedRow',
  data() {
    return {
      name: "Elvin Limpin",
      description: "Full Stack Developer | UCalgary CS Alumni | YouTube Creator | Musician | Athlete",
      imgURL: 'selfie.jpg'
    }
  }
};
</script>

<style scoped>
  .row {
    margin-top:3em;
  }

  p {
    font-size: 0.9em;
  }

  img {
    border: 4px solid #f0f0f0;
    border-radius:50%;
    max-width: 200px;
    text-align: center;
    object-fit: cover;

    position: relative;
    left: -50%;
    float: left;
  }

  .img-container{
    float: left;
    left: 50%;
    position: relative;
    max-width:225px;
    text-align:center;
  }
</style>
