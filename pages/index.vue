<template>
  <main>
  {{  data  }}
  </main>
</template>
 

<script setup lang="ts">
const data = await queryContent('/hello').findOne()
</script>
