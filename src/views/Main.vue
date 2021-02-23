<template>
  <div class="Main">
    <!-- <img alt="Vue logo" src="../assets/geeks-logo.svg" width="500" style="background-color: grey"/> -->
    <Slideshow></Slideshow>
  </div>
</template>

<script>
// @ is an alias to /src
import Slideshow from "@/components/Slideshow.vue";

export default {
  name: "Main",
  components: {
    Slideshow
  }
};
</script>
