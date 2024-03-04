# Content v2 / nuxt 3 

Bug (potentially related to nitro) using `queryContent` in nuxt/content

## Setup

```bash
santiago@macbook content-app % pnpm nuxi info

------------------------------
- Operating System: Darwin
- Node Version:     v21.2.0
- Nuxt Version:     3.10.3
- CLI Version:      3.10.1
- Nitro Version:    2.9.1
- Package Manager:  pnpm@8.9.2
- Builder:          -
- User Config:      devtools, modules, content
- Runtime Modules:  @nuxt/content@2.12.0
- Build Modules:    -
------------------------------
```

## Production build error:

```bash
[GET] "/api/query/yFRQI29ykM.1709594450379.json?_params=%7B%22first%22:true,%22where%22:%5B%7B%22_path%22:%22%2Fhello%22%7D%5D,%22sort%22:%5B%7B%22_file%22:1,%22$numeric%22:true%7D%5D%7D": 500
```


## Json content:


```json
{
  "title": "Hello Content v2!",
  "description": "The writing experience for Nuxt 3",
  "category": "announcement"
}
```

## Vue SFC:


```html
<template>
  <main>
  {{  data  }}
  </main>
</template>

<script setup lang="ts">
const data = await queryContent('/hello').findOne()
</script>
```


