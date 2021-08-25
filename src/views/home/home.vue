<template>
  <div id="home">
    <header>
      <van-search
        v-model="searchValue"
        show-action
        placeholder="请输入搜索关键词"
        @focus="onSearchFocus"
        @search="onSearch"
      >
        <template #action>
          <div @click="onSearch">搜索</div>
        </template>
      </van-search>
    </header>
    <nav>
      <van-swipe :autoplay="3000">
        <van-swipe-item v-for="(image, index) in images" :key="index">
          <img :src="image" class="img_fill"/>
        </van-swipe-item>
      </van-swipe>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchValue: "",
      images: [
        'https://img01.yzcdn.cn/vant/apple-1.jpg',
        'https://img01.yzcdn.cn/vant/apple-2.jpg',
      ],
    };
  },
  methods: {
    // 焦点搜索框弹出输入框
    onSearchFocus() {},
  },
};
</script>

<style lang="less" scoped>
#home {
  header {
    width: 100%;
    height: 1.95rem;
    position: fixed;
    top: 0;
    z-index: 100;
    padding: 0 1rem;
  }
  nav {
    width: 100%;
    height: 10rem;
    padding-top: 2.5rem;
    .van-swipe {
        width: 100%;
        height: 100%;
    }
  }
}
</style>
