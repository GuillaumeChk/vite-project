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
