<template>
  <q-layout view="hHh Lpr fFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="sidebarOpen = !sidebarOpen"
        />

        <q-avatar>
          <img src="favicon.png" />
        </q-avatar>
        <q-toolbar-title>
          NMApp
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <!-- Mobile Sidebar -->
    <q-drawer
      v-if="($q.platform.is.mobile || $q.platform.is.nativeMobile || $q.platform.is.nativeMobileWrapper)"
      v-model="sidebarOpen"
      show-if-above

      :width="200"
      :breakpoint="550"
      class="bg-primary">
      <q-scroll-area class="fit">
        <SidebarContent />
      </q-scroll-area>
    </q-drawer>
    <!-- Desktop Sidebar -->
    <q-drawer
      v-else
      show-if-above
      persistent

      :mini="!sidebarOpen"

      :breakpoint="0"
      class="bg-primary">
      <q-scroll-area class="fit">
        <SidebarContent />
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <keep-alive>
        <router-view />
      </keep-alive>
    </q-page-container>

    <q-footer elevated class="row q-pt-sm q-pl-md q-pr-md q-pb-sm">
      <div class="col text-left">
        Left
      </div>
      <div class="col text-right">
        Right
      </div>
    </q-footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue';
import SidebarContent from "layouts/SidebarContent";

export default {
  components: {SidebarContent},
  props: {
    sidebarOpen: ref(false),
  }
}


</script>
