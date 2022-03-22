<template>
  <div>
    <div class="loader">
      <span v-for="i in 9" :key="i" class="loader-block"></span>
    </div>
  </div>
</template>
<script>
export default {
  name: "LoadingCustom",
};
</script>
