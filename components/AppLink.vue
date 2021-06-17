<template>
  <div>
    <nuxt-link :to="app.route">
      {{ route }}
      <div
        class="
          p-6
          max-w-sm
          mx-auto
          bg-white
          rounded-xl
          shadow-lg
          flex
          items-center
          space-x-4
        "
      >
        <div class="flex-shrink-0">
          <h2 data-test-icon class="text-5xl">{{ app.icon }}</h2>
        </div>
        <div>
          <div data-test-title class="text-xl font-medium text-black">
            {{ app.title }}
          </div>
          <p data-test-description class="text-gray-500">
            {{ app.description }}
          </p>
        </div>
      </div>
    </nuxt-link>
  </div>
</template>
<script lang="ts">
import Vue, { PropOptions } from 'vue'
import App from 'AppType'
// interface App {
//   route: string
//   icon: string
//   title: string
//   description: string
// }

export default Vue.extend({
  name: 'AppLink',

  props: {
    app: {
      type: Object,
      required: true,
    } as PropOptions<App>,
  },

  data() {
    return {
      message: 'This is a message',
    }
  },

  computed: {
    route(): number {
      return this.app.route
    },
  },
})
</script>
<style lang=""></style>
