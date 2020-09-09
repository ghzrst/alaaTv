<template>
   <div class="mt-3 carousel-container">
    <b-carousel
      id="carousel-1"
      v-model="slide"
      :interval="4000"
      controls
      indicators
      background="#ababab"
      img-width="1024"
      img-height="480"
      style="text-shadow: 1px 1px 2px #333;"
      @sliding-start="onSlideStart"
      @sliding-end="onSlideEnd"
    >
      <b-carousel-slide
        img-src="https://cdn.alaatv.com/upload/images/slideShow/abrisham_slide_home2_20200906124025.jpg?w=965&amp;h=376"
      ></b-carousel-slide>

      <b-carousel-slide img-src="https://cdn.alaatv.com/upload/images/slideShow/madrese_online_slide_20190902113043.jpg?w=965&amp;h=376">
      </b-carousel-slide>
    </b-carousel>
  </div>
</template>
<script>
export default {
  name: "Carousel",
  data() {
      return {
        slide: 0,
        sliding: null
      }
    },
    methods: {
      onSlideStart() {
        this.sliding = true
      },
      onSlideEnd() {
        this.sliding = false
      }
    }
};
</script>