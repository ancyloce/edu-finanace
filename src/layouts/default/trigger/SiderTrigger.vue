<template>
  <div @click.stop="toggleCollapsed">
    <DoubleRightOutlined v-if="getCollapsed" />
    <DoubleLeftOutlined v-else />
    <span v-if="!getCollapsed" class="trigger-text">{{ t('layout.footer.puttingNavigate') }}</span>
  </div>
</template>
<script lang="ts" setup>
  import { DoubleRightOutlined, DoubleLeftOutlined } from '@ant-design/icons-vue';
  import { useMenuSetting } from '@/hooks/setting/useMenuSetting';
  import { useI18n } from '@/hooks/web/useI18n';

  const { t } = useI18n();

  console.log('SiderTrigger', t('layout.footer.puttingNavigate'));

  const { getCollapsed, toggleCollapsed } = useMenuSetting();
</script>

<style lang="less">
  .trigger-text {
    padding-left: 4px;
  }
</style>
