<template>
  <div class="vertical-layout h-100" :class="[layoutClasses]" :data-col="isNavMenuHidden ? '1-column' : null">
    <!-- Navbar -->
    <b-navbar
      :toggleable="false"
      :variant="navbarBackgroundColor"
      class="header-navbar navbar navbar-shadow align-items-center"
      :class="[navbarTypeClass]"
    >
      <Header-2 :toggle-vertical-menu-active="toggleVerticalMenuActive" />
      <Header :toggle-vertical-menu-active="toggleVerticalMenuActive" />
    </b-navbar>

    <!-- Navbar -->

    <!-- Sidebar Menu -->
    <!-- <SidebarMenu
      v-if="!isNavMenuHidden"
      :is-vertical-menu-active="isVerticalMenuActive"
      :toggle-vertical-menu-active="toggleVerticalMenuActive"
    >
      <template #header="slotProps">
        <slot name="vertical-menu-header" v-bind="slotProps" />
      </template>
    </SidebarMenu> -->
    <!-- Sidebar Menu -->

    <!-- Sidebar Menu Overlay -->
    <div class="sidenav-overlay" :class="overlayClasses" @click="isVerticalMenuActive = false" />
    <!-- Sidebar Menu Overlay -->

    <!-- Content -->

    <!-- CONTENT TYPE: Left -->
    <!-- <transition :name="routerTransition" mode="out-in">
      <component
        :is="layoutContentRenderer"
        :key="
          layoutContentRenderer === 'layout-content-renderer-left' ? $route.meta.navActiveLink || $route.name : null
        "
      >
        <template v-for="(index, name) in $scopedSlots" #[name]="data">
          <slot :name="name" v-bind="data" />
        </template>
      </component>
    </transition> -->
    <!-- / Content -->

    <!-- <Header /> -->
    <Footer />
  </div>
</template>
<script>
// import Breadcrumb from '@/layouts/components/Breadcrumb.vue';
import { BNavbar } from 'bootstrap-vue';
import { reactive } from '@vue/composition-api';
import Header from '@/layouts/components/Header.vue';
import Header2 from '~/layouts/components/Header-2.vue';
import Footer from '@/layouts/components/Footer.vue';
// import SidebarMenu from '@/layouts/components/SidebarMenu.vue';

export default {
  components: {
    BNavbar,
    Header,
    Header2,
    Footer,
    // SidebarMenu,
  },
  setup() {
    const layoutClasses = reactive('vsvs');
    const isNavMenuHidden = reactive(false);
    const navbarTypeClass = reactive('floating-nav');
    const scrolledTo = reactive(true);
    const skin = reactive('light');
    const isVerticalMenuActive = reactive(true);
    // const toggleVerticalMenuActive = reactive(false);
    // const { skin, navbarType, footerType, routerTransition, isNavMenuHidden } = useAppConfig();

    const toggleVerticalMenuActive = () => {
      isVerticalMenuActive.value = !isVerticalMenuActive.value;
    };

    const navbarBackgroundColor = reactive('');
    return {
      layoutClasses,
      skin,
      scrolledTo,
      navbarTypeClass,
      isNavMenuHidden,
      isVerticalMenuActive,
      toggleVerticalMenuActive,
      navbarBackgroundColor,
    };
  },
};
</script>

<style lang=""></style>
