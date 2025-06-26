<script setup lang="ts">
const route = useRoute()
const slug = (route.params.slug as string[]).join('/')

if (slug) {
  const { error } = await useFetch(`/api/link/query?slug=${slug}`)

  if (error.value) {
    await navigateTo('https://theblueground.com', {
      external: true,
      redirectCode: 302,
    })
  }
}
</script>

<template>
  <div></div>
</template> 