<script lang="ts">
import { defineComponent, reactive, toRefs } from 'vue';
import type { MenuProps } from 'ant-design-vue';
import PurchaseIcon from '@/components/icons/PurchaseIcon.vue';
import DashboardIcon from "@/components/icons/DashboardIcon.vue";
import ApproveIcon from "@/components/icons/ApproveIcon.vue";
import RequestsIcon from "@/components/icons/RequestsIcon.vue";
import QuotesIcon from "@/components/icons/QuotesIcon.vue";
import PaymentsIcon from "@/components/icons/PaymentsIcon.vue";
import AddIcon from "@/components/icons/AddIcon.vue";
import DropDownIcon from "@/components/icons/DropDownIcon.vue";
export default defineComponent({
  components: {
    DropDownIcon,
    AddIcon,
    PaymentsIcon,
    QuotesIcon,
    RequestsIcon,
    ApproveIcon,
    DashboardIcon,
    PurchaseIcon,
  },
  setup() {
    const state = reactive({
      selectedKeys: [],
      openKeys: [],
    });
    const handleClick: MenuProps['onClick'] = menuInfo => {
      console.log('click ', menuInfo);
    };
    return {
      ...toRefs(state),
      handleClick,
    };
  },
});
</script>
<template>
  <a-menu
    v-model:openKeys="openKeys"
    v-model:selectedKeys="selectedKeys"
    class="account-menu"
    mode="vertical"
    theme="dark"
    @click="handleClick"
  >
    <a-menu-item class="button-menu-item" key="0">
      <a-button type="primary" class="request-btn">
        <AddIcon  />
        New Request
        <a-divider type="vertical" />
        <DropDownIcon />
      </a-button>
    </a-menu-item>
    <a-menu-item key="1">
      <DashboardIcon />
      Dashboard
    </a-menu-item>
    <a-menu-item key="2">
      <ApproveIcon />
      Approve
    </a-menu-item>
    <a-menu-item key="3">
      <RequestsIcon />
      Requests
    </a-menu-item>
    <a-menu-item key="4">
      <QuotesIcon />
      Quotes
    </a-menu-item>
    <a-menu-item key="5">
      <PurchaseIcon />
      Purchase Orders
    </a-menu-item>
    <a-menu-item key="6">
      <PaymentsIcon />
      Payments
    </a-menu-item>
    <AMenuDivider />
    <AMenuItemGroup title="Analytics">
      <a-sub-menu key="sub1">
        <template #title>Reports</template>
        <a-menu-item key="sub1-3">Option 3</a-menu-item>
        <a-menu-item key="sub1-4">Option 4</a-menu-item>
        <a-sub-menu key="sub1-2" title="Submenu">
          <a-menu-item key="sub1-5">Option 5</a-menu-item>
          <a-menu-item key="sub1-6">Option 6</a-menu-item>
        </a-sub-menu>
      </a-sub-menu>
      <a-sub-menu key="sub2">
        <template #title>Insights</template>
        <a-menu-item key="sub2-3">Option 3</a-menu-item>
        <a-menu-item key="sub2-4">Option 4</a-menu-item>
        <a-sub-menu key="sub1-2" title="Submenu">
          <a-menu-item key="sub2-5">Option 5</a-menu-item>
          <a-menu-item key="sub2-6">Option 6</a-menu-item>
        </a-sub-menu>
      </a-sub-menu>
    </AMenuItemGroup>
    <AMenuDivider />
    <AMenuItemGroup title="Management">
      <a-menu-item key="7">
        Supplier
      </a-menu-item>
      <a-menu-item key="8">
        Employee
      </a-menu-item>
      <a-menu-item key="9">
        Admin
      </a-menu-item>
    </AMenuItemGroup>
  </a-menu>
</template>

<style>
  .ant-menu.ant-menu-root.ant-menu-vertical.ant-menu-dark.account-menu {
    width: 194px;
    background: #383E54;
    border-right: 0;
    height: 100%;
    overflow-y: scroll;
  }

  .account-menu > .ant-menu-item.button-menu-item.ant-menu-item-only-child {
    height: 100px;
    margin-bottom: 12px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .ant-menu-item.button-menu-item.ant-menu-item-only-child > span > button.request-btn {
    font-size: 13px;
    font-weight: 600;
    line-height: 18px;
    letter-spacing: 0;
    display: flex;
    align-items: center;
    flex-wrap: nowrap;
    padding: 12px 0 10px 12px;
    height: unset;
  }

  .request-btn {
    width: 159px;
    background: #03C3D8;
    border-radius: 4px;
  }

  .request-btn > svg {
    margin-right: 11px;
  }

  .request-btn > .ant-divider {
    margin: -10px 12px;
  }

  .account-menu > .ant-menu-item,.ant-menu-item.ant-menu-item-only-child {
    display: flex;
  }

  .account-menu > .ant-menu-item > span,.ant-menu-submenu-title,.ant-menu-item-group-list > .ant-menu-item.ant-menu-item-only-child > span {
    display: flex;
    padding-left: 7px;
    justify-content: flex-start;
    font-size: 15px;
    font-weight: 600;
    line-height: 20px;
    gap: 14px;
    letter-spacing: 0;
    align-items: center;
    color: #FFFFFF;
  }

  .ant-menu-item-group-list > .ant-menu-item.ant-menu-item-only-child > span {
    padding: 0;
  }

  div.ant-menu-item-group-title {
    font-size: 12px;
    font-weight: 400;
    line-height: 16px;
    letter-spacing: 0;
    text-transform: uppercase;
    opacity: 0.49;
    padding-top: 25px;
  }

</style>