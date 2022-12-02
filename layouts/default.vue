<template>
  <div class="bg-image">
    <slot />
  </div>
</template>

<style scoped>

.bg-image {
  background-image: url('~/images/background.png');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}


</style>