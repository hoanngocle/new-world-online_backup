<template>
  <footer class="footer footer-light footer-static">
    <slot name="footer">
      <p class="clearfix mb-0">
        <span class="float-md-left d-block d-md-inline-block mt-25">
          COPYRIGHT © {{ new Date().getFullYear() }}
          <b-link class="ml-25" href="https://github.com/hoanngocle" target="_blank">New World Online</b-link>
          <span class="d-none d-sm-inline-block">, All rights Reserved</span>
        </span>

        <span class="float-md-right d-none d-md-block"
          >Hand-crafted &amp; Made with
          <feather-icon icon="HeartIcon" size="21" class="text-danger stroke-current" />
        </span>
      </p>
    </slot>
  </footer>
</template>

<script>
import { BLink } from 'bootstrap-vue';

export default {
  components: {
    BLink,
  },
};
</script>
