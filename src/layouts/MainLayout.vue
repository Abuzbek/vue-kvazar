<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title>
          AbuzCoder
        </q-toolbar-title>
      </q-toolbar>
    </q-header>
    <q-drawer
        v-model="leftDrawerOpen"
        show-if-above
        :width="300"
        :breakpoint="700"
      >
        <q-scroll-area style="height: calc(100% - 150px); margin-top: 150px; border-right: 1px solid #ddd">
          <q-list padding>
            <EssentialLink
            v-for="link in essentialLinks"
            :key="link.title"
            v-bind="link"
           />
          </q-list>
        </q-scroll-area>

        <q-img class="absolute-top" src="https://cdn.pixabay.com/photo/2015/07/27/18/50/scene-863040_1280.jpg" style="height: 150px">
          <div class="absolute-bottom bg-transparent">
            <q-avatar size="56px" class="q-mb-sm">
              <img src="~assets/logo.png">
            </q-avatar>
            <div class="text-weight-bold text-black">AbuzCoder</div>
            <div class="text-black">@AbuzCoder</div>
          </div>
        </q-img>
      </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Simple Site',
    icon: 'public',
    link: '/'
  },
  {
    title: 'Help',
    icon: 'help',
    link: '/help'
  }
]

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>
