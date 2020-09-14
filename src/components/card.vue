<template>
    <div class="col-lg-3 col-sm-6 col-12 q-mb-lg"
        style="padding:0px 15px"
        >
        <q-card class="my-card">
          <q-img :src="img" clickable
                v-ripple
            />

          <q-card-section>
            <q-btn
              fab
              color="secondary"
              icon="place"
              class="absolute"
              style="top: 0; right: 12px; transform: translateY(-50%);"
            />

            <div class="row no-wrap items-center">
              <div class="col text-h6 ellipsis">
                 {{headerText1}}
              </div>
              <div class="col-auto text-grey text-caption q-pt-md row no-wrap items-center">
                <q-icon name="place" />
                250 ft
              </div>
            </div>

            <q-rating v-model="stars" :max="5" size="32px" />
          </q-card-section>

          <q-card-section class="q-pt-none">
            <div class="text-subtitle1">
              {{headerText2}}
            </div>
            <div class="text-caption text-grey">
              Small plates, salads & sandwiches in an intimate setting.
            </div>
          </q-card-section>

          <q-separator />
        </q-card>
      </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    headerText1: {
      type: String,
      required: true
    },

    img: {
      type: String,
      required: true
    },

    headerText2: {
      type: String,
      required: true
    }
  },
  data () {
    return {
      stars: 4
    }
  }
}
</script>
