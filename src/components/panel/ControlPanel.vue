<script lang="ts">

import FilterIcon from "@/components/icons/FilterIcon.vue";
import {defineComponent} from "vue";
import CustomizeIcon from "@/components/icons/CustomizeIcon.vue";
import ExportIcon from "@/components/icons/ExportIcon.vue";

export default defineComponent({
  components: {ExportIcon, CustomizeIcon, FilterIcon},
})

</script>

<template>
  <a-row class="panel-bar"  type="flex">
    <a-col :span="4">
      <a-typography-title class="account-section-title" :level="2">Invoices</a-typography-title>
    </a-col>
    <a-col :span="20">
      <a-row class="control-panel-bar" type="flex" justify="end">
        <a-col :span="4">
          <a-button class="panel-btn" type="text" >
            <FilterIcon />
            Filter
          </a-button>
        </a-col>
        <a-col :span="4">
          <a-button class="panel-btn" type="text" >
            <CustomizeIcon />
            Customize
          </a-button>
        </a-col>
        <a-col :span="4">
          <a-button class="panel-btn" type="text" >
            <ExportIcon />
            Export
          </a-button>
        </a-col>
        <a-col :span="4">
          <a-button class="panel-btn-new" type="primary" >
            New
          </a-button>
        </a-col>
      </a-row>
    </a-col>
  </a-row>
</template>

<style scoped>
.account-section-title {
  margin: 0;
  font-size: 32px;
  font-weight: 300;
  line-height: 44px;
  letter-spacing: 0;
  text-align: left;
}

.control-panel-bar {
  align-items: center;
}

.panel-bar {
  width: 100%;
}

.panel-btn {
  font-size: 16px;
  font-weight: 600;
  line-height: 22px;
  letter-spacing: 0;
  text-align: left;
  color: #008897;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
  gap: 10px;
}

.panel-btn-new {
  background: #008897;
  border-radius: 4px;
  border: none;
  padding: 9px 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 40px;
  font-size: 16px;
  font-weight: 600;
  line-height: 22px;
  letter-spacing: 0;
  text-align: left;
}
</style>
