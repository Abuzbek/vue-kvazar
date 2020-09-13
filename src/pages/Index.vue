<template>
  <q-page>
    <div class="row">
      <div class="col-12">
        <div class="text-h3 text-center q-pt-lg q-mb-lg text-amber">
          Welocome First My Project !!!
        </div>
        <div class="q-pa-md">
        <q-carousel
          animated
          v-model="slide"
          transition-prev="scale"
          transition-next="scale"
          swipeable
          v-ripple
          arrows
          navigation
          infinite
        >
          <q-carousel-slide :name="1" img-src="https://mdbootstrap.com/img/Photos/Slides/img%20(6).jpg" />
          <q-carousel-slide :name="2" img-src="https://mdbootstrap.com/img/Photos/Slides/img%20(8).jpg" />
          <q-carousel-slide :name="3" img-src="https://mdbootstrap.com/img/Photos/Slides/img%20(24).jpg" />
          <q-carousel-slide :name="4" img-src="https://mdbootstrap.com/img/Photos/Slides/img%20(152).jpg" />
        </q-carousel>
      </div>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      slide: 1
    }
  }
}
</script>
