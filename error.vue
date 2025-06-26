<script setup lang="ts">
import type { NuxtError } from '#app'
import errorImage from './assets/images/404.svg?raw'

const props = defineProps({
  error: Object as () => NuxtError
})

if (props.error?.statusCode === 404) {
  clearError({ redirect: 'https://theblueground.com' })
}
</script>

<template>
  <NuxtLayout name="default">
    <a
      class="w-full h-full max-w-[600px] mx-auto flex items-center justify-center [&_svg]:w-full"
      href="/"
      v-html="errorImage"
    />
  </NuxtLayout>
</template>
