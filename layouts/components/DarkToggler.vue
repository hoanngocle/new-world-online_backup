<template>
  <b-nav-item @click="mode = 'light' ? 'light' : 'dark'">
    <feather-icon size="21" :icon="`${isDark ? 'Sun' : 'Moon'}Icon`" />
  </b-nav-item>
</template>

<script>
// import useAppConfig from '@core/app-config/useAppConfig';
// import { computed } from '@vue/composition-api';
import { BNavItem } from 'bootstrap-vue';

export default {
  components: {
    BNavItem,
  },
  setup() {
    // const { skin } = useAppConfig();
    const mode = {
      value: 'light',
    };

    // const isDark = computed(() => mode.value === 'dark');
    const isDark = 'light';
    return { mode, isDark };
  },
};
</script>
