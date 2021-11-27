<template>
  <div>
    <!-- <Header /> -->
    <Breadcrumb />
    <Navbar />
    <div>My blog navigation bar here</div>
    <Nuxt />
    <Footer />
  </div>
</template>
<script>
import Breadcrumb from '@/layouts/components/Breadcrumb.vue';
import Navbar from '@/layouts/components/Navbar.vue';
import Footer from '@/layouts/components/Footer.vue';

export default {
  components: {
    Breadcrumb,
    Navbar,
    Footer,
  },
};
</script>

<style lang=""></style>
