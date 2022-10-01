From a default project vue cli with vite  
- Added images folder in Assets folder  
 - Added images  
- Modified About.vue view  like below

About.vue

```
<template>
  <div>
    <img
    v-for="url in imagesUrl"
    :key="url.name"
      :src="getImageUrl(url.name)"
      style="width: 50px; height: 50px"
    />
  </div>
</template>

<script setup>
function getImageUrl(subPath) {
  return new URL(`${subPath}`, import.meta.url).href;
}

let imagesUrl =  import.meta.glob("../assets/images/*.(jpg|JPG|png|PNG|svg)", { as: "url" });
</script>
```

### Reproduce   ###
`npm run build`

### Error ###
```
vite v3.1.4 building for production...
✓ 17 modules transformed.
[vite:import-glob] EPERM: operation not permitted, scandir 'C:\Documents and Settings'
file: C:/Users/guill/Desktop/web dev freelance/vite-project/vue-project/src/views/AboutView.vue
error during build:
Error: EPERM: operation not permitted, scandir 'C:\Documents and Settings'
```
