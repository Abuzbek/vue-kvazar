<template>
  <q-page>
    <div class="row q-pb-xl">
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
      <div class="col-12">
        <div class="text-h3 text-warning q-py-xl text-center">
          Cards
        </div>
      </div>
      <div class="col-12">
        <div class="row justify-center">
        <div class="col-lg-6 col-md-8 col-sm-10 col-12 q-px-lg q-pb-sm bg-grey-3 q-mb-lg q-pb-lg q-pt-0 ">
            <div class="text-white cardHeader q-mt-sm q-py-sm col text-h4 text-center bg-blue-grey">
              ADD CARDS
            </div>
            <!-- cards push input v-model{text} -->
              <q-input
                v-model="text"
                label="Card Header"
                class="q-mb-lg"
              />
            <!-- cards push input v-model{text} -->
            <!-- cards push input v-model{textTwo} -->
              <q-input
                v-model="textTwo"
                label="Card Header"
                class="q-mb-lg"
              />
            <!-- cards push input v-model{textTwo} -->
              <!-- cards push button -->
              <div>
                <q-btn push color="primary" label="Push" icon="add" @click="newCadrs" />
              </div>
              <!-- cards push button -->
        </div>
        </div>
      </div>
        <Card
          v-for="link in essentialLinks"
          :key="link.headerText1"
          v-bind="link"
        />
    </div>
  </q-page>
</template>

<script>
import Card from 'components/card.vue'
const cards = [
  {
    headerText1: 'Card Title 1',
    headerText2: 'public 1',
    img: 'https://mdbootstrap.com/img/Photos/Horizontal/E-commerce/new/img(13).jpg'
  },
  {
    headerText1: 'Card Title 2',
    headerText2: 'public 2',
    img: 'https://mdbootstrap.com/img/Photos/Horizontal/E-commerce/new/img(14).jpg'
  },
  {
    headerText1: 'Card Title 3',
    headerText2: 'public 3',
    img: 'https://mdbootstrap.com/img/Photos/Horizontal/E-commerce/new/img(6).jpg'
  },
  {
    headerText1: 'Card Title 4',
    headerText2: 'public 4',
    img: 'https://mdbootstrap.com/img/Photos/Horizontal/E-commerce/new/img(3).jpg'
  }
]
export default {
  name: 'PageIndex',
  components: { Card },
  data () {
    return {
      slide: 1,
      essentialLinks: cards,
      stars: 4,
      text: '',
      textTwo: '',
      ph: '',
      dense: false
    }
  },
  methods: {
    newCadrs () {
      this.$q.notify("Card qo'shildi!!!")
      cards.push({
        headerText1: this.text,
        headerText2: this.textTwo,
        img: 'https://source.unsplash.com/random/700x467'
      })
      this.text = ''
      this.textTwo = ''
    }
  }
}
</script>
<style lang="scss">
  .cardHeader{
    border-radius:10px;
  }
</style>
