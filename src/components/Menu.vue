<template functional>
  <a-sub-menu :key="props.menuInfo.key">
    <span slot="title">
      <a-icon :type="props.menuInfo.icon" v-if="props.menuInfo.icon"/>
      <span>{{props.menuInfo.title}}</span>
    </span>

    <template v-for="item in props.menuInfo.children">
      <a-menu-item v-if="!item.children" :key="item.key">
        <a-icon :type="item.icon" v-if="item.icon"/>
        <span>{{item.title}}</span>
      </a-menu-item>

      <sub-menu v-else :menu-info="item" :key="item.key"/>
    </template>
  </a-sub-menu>
</template>

<script>
export default {
  props: ["menuInfo"]
};
</script>