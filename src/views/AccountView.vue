<script lang="ts">
import Menu from "@/components/menu/Menu.vue";
import ControlPanel from "@/components/panel/ControlPanel.vue";
import InvoicesTable from "@/components/table/InvoicesTable.vue";
export default {
  components: {
    InvoicesTable,
    Menu,
    ControlPanel,
  },
};
</script>

<template>
  <main>
    <Menu />
      <a-row class="main-content" type="flex">
        <ControlPanel />
        <InvoicesTable />
      </a-row>
  </main>
</template>

<style>
  .main-content {
    padding: 40px 38px;
    display: flex;
    height: 100%;
    width: 80%;
  }

  main {
    display: flex;
    height: 100%;
    justify-content: space-between;
  }

  body {
    background: #F5F5F5 !important;
  }
</style>
