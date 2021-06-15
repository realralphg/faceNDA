<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title>
          Face NDA
        </q-toolbar-title>

        <q-btn
          class="button"
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />
      </q-toolbar>
    </q-header>

    <q-footer class="text-center">
      Face NDA
    </q-footer>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Face NDA
        </q-item-label>

        <q-item v-for="link in linksData" :key="link.title">          

            <q-item-section avatar>
              <q-icon :name="link.icon"></q-icon>
            </q-item-section>

            <q-item-section>
              <q-item-label>{{ link.title }}</q-item-label>
            </q-item-section>          

        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
  export default {
    name: 'MainLayout',

    data () {
      return {
        leftDrawerOpen: false,
        linksData : [
          {
            icon: 'public',
            title: 'Camera On',          
          },
          {
            icon: 'favorite',
            title: 'About the Project',                  
          }
        ]
      }
    }

  }
</script>
