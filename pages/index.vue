<template>
  <div>
    <div class="bg-blue-100 flex flex-col">
      <div class="flex justify-end mr-10 mt-4">
        <span class="mr-4"
          ><img class="flag" alt="USA flag" src="usa.png"
        /></span>
        <span><img class="flag" alt="Brazillian flag" src="brazil.png" /></span>
      </div>

      <div class="w-full flex justify-center items-center mt-8 mb-20">
        <img
          role="presentation"
          alt=""
          class="rounded-full border-2 border-blue-900"
          src="https://avatars.githubusercontent.com/u/20529578?v=4"
        />
        <div class="ml-20">
          <h1 class="text-5xl font-bold text-blue-900">Mateus Valgueiro</h1>

          <ul class="text-2xl">
            <li class="mt-10">
              🎓 Graduated in Computer Engineering at CIn - UFPE
            </li>

            <li class="mt-5">💻 Working as a Software Engineer at C.E.S.A.R</li>

            <li class="ml-1.5 mt-5">📍 Recife - Pernambuco - Brazil</li>
          </ul>
        </div>
      </div>
    </div>

    <div class="container mx-auto flex flex-col justify-center mt-10 pb-10">
      <h3 class="text-4xl font-bold text-center text-blue-900">Apps</h3>
      <ul class="mt-4">
        <li v-for="(app, index) in apps" :key="index">
          <app-link :app="app"></app-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import App from '@types/app'

export default Vue.extend({
  asyncData(): { apps: Array<App> } {
    return {
      apps: [
        {
          route: 'mirror',
          icon: '🎙',
          title: 'Voice Mirror',
          description: 'Check if your mic is working correctly',
        },
      ],
    }
  },
})
</script>

<style>
.flag {
  width: 36px;
}
</style>
