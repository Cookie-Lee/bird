<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-white glossy text-black">
        <router-link to="/">
          <q-avatar>
            <img src="/logo.png" />
          </q-avatar>
        </router-link>
        <q-toolbar-title>
          <span style="font-size: 32px">是個鳥研究呢</span>
        </q-toolbar-title>
        <q-space />
        <q-btn
          stretch
          flat
          label="數鳥"
          size="1.5rem"
          padding="0 1rem"
          :to="{ path: '/countbird' }"
        />
        <q-btn
          stretch
          flat
          label="預測"
          size="1.5rem"
          padding="0 1rem"
          :to="{ path: '/predict' }"
        />
        <q-btn
          stretch
          flat
          label="建議"
          size="1.5rem"
          padding="0 1rem"
          @click="openGoogleForm"
        />
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <div class="bg-grey-10 text-white flex flex-center q-py-md">
      <span class="q-mr-lg">
        是個鳥研究呢 &copy; {{ new Date().getFullYear() }}
      </span>
      <span> 研究員: 台北教育大學 李秉剛 21108X007</span>
    </div>
  </q-layout>
</template>

<script>
export default {
  name: "MainLayout",
  data() {
    return {};
  },
  methods: {
    openGoogleForm() {
      window.open("https://forms.gle/VeUBVXipe13FQijs8", "_blank").focus();
    },
  },
};
</script>

<style>
@font-face {
  font-family: "Helvetica";
  src: url("../assets/font/ChenYuluoyan-Thin.woff") format("woff");
}

body {
  font-family: "Helvetica";
}
</style>
