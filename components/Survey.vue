<template>
  <div class="w-full" v-if="shouldShowSurvey">
    <a :href="link" target="_blank" rel="noopener">
      <img :src="mobileImage" class="block lg:hidden" alt="Survey" />
      <img :src="desktopImage" class="hidden lg:block" alt="Survey" />
    </a>
  </div>
</template>

<script>
export default {
  props: {
    desktopImage: {
      type: String,
      required: true
    },
    mobileImage: {
      type: String,
      required: true
    },
    link: {
      type: String,
      required: true
    },
    expiresOn: {
      type: String,
      required: true
    }
  },
  computed: {
    shouldShowSurvey() {
      return Date.now() < new Date(this.expiresOn).getTime();
    }
  }
};
</script>

<style scoped></style>
