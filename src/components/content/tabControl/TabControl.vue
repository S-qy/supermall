<!--
 * @Author: 孙秋云
 * @Date: 2020-06-15 14:28:48
 * @LastEditTime: 2021-05-09 19:19:48
 * @LastEditors: Please set LastEditors
 * @Description: 导航选项卡
 * @FilePath: \MiniSuper\src\components\content\tabControl\TabControl.vue
-->

<template>
  <div class="tab-control">
    <div v-for="(item,index) in titles" class="tab-control-item" :class="{active:index===currentIndex }" @click="itemClick(index)" >
      <span>{{ item }}</span>
    </div>
  </div>
</template>

<script>
//商品切换的tabControl
export default {
  props: {
    titles: {
      type: Array,
      default() {
        return [];
      }
    }
  },
  data() {
    return {
      currentIndex: 0
    };
  },
  methods: {
    itemClick(index) {
      this.currentIndex = index;
      this.$emit('tabClick',index);
    }
  }
};
</script>

<style>
.tab-control {
  display: flex;
  text-align: center;
  height: 44px;
  line-height: 44px;
  font-size: 15px;
  background-color:#fff;
}
.tab-control span {
  padding: 4px;
}
.active {
  color: #ff5777;
}
.active span {
  border-bottom: 2px solid #ff8198;
}
.tab-control-item {
  flex: 1;
}
</style>
