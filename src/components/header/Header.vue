<script lang="ts">
import {useRoute} from "vue-router";
import LogoThemeWhite from "@/components/icons/LogoThemeWhite.vue";
import LogoThemeDark from "@/components/icons/LogoThemeDark.vue";
import { defineComponent, ref } from 'vue';

export default defineComponent({
  methods: {useRoute},
  components: {LogoThemeWhite, LogoThemeDark},
  setup() {
    const value = ref('');
    const onSearch = (searchValue: string) => {
      console.log('use value', searchValue);
      console.log('or use this.value', value.value);
    };
    return {
      value,
      onSearch,
    };
  },
});
</script>


<template>
  <header :class="{ accountStyle: useRoute().path === '/account'}">
    <template v-if="useRoute().path === '/account'">
      <LogoThemeDark
        class="logo"
      />
      <a-input-search
        v-model:value="value"
        placeholder="input search text"
        style="width: 200px;margin-left: 58px;"
        @search="onSearch"
      />
    </template>
    <template v-else>
      <LogoThemeWhite class="logo-white" />
    </template>

  </header>
</template>

<style>
header {
  padding: 59px 74px 0;
}

.logo-white {
  margin-right: 58px;
}

.accountStyle {
  padding: 17px 36px 22px;
  background-color: #FFFFFF;
}
</style>