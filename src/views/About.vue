<template>
  <div class="about">
    <ion-header>
      <ion-toolbar>
        <ion-title>Images</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-img :src="imageSrc"></ion-img>
    <ion-button expand="block" @click="$router.go(-1)">Back</ion-button>
  </div>
</template>

<script>
export default {
  props:['imageSrc']
}
</script>

