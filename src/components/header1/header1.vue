<template>
  <div class="top_menu_bar ">
      <v-title>toutiao</v-title>
      <ul class="top_menu_bar_ul">
        <router-link 
            v-for="(item, index) in nav" 
            class="home_nav_item" 
            :key="index"
            :to="item.url + '/' +item.type"
            tag="li"
            >{{item.text}}
        </router-link>
      </ul>
  </div>
</template>
<script>
import VTitle from '@/components/title/title'
export default {
  data () {
    return {
         nav: [
				{url: '/indexList', type: '__all__', text: '推荐'},
				{url: '/indexList', type: 'news_hot', text: '热点'},
				{url: '/indexList', type: 'news_society', text: '社会'},
				{url: '/indexList', type: 'news_entertainment', text: '娱乐'},
				{url: '/indexList', type: 'news_tech', text: '科技'},
				{url: '/indexList', type: 'news_car', text: '汽车'},
				{url: '/indexList', type: 'news_sports', text: '体育'},
				{url: '/indexList', type: 'news_finance', text: '财经'},
				{url: '/indexList', type: 'news_military', text: '军事'},
				{url: '/indexList', type: 'news_world', text: '国际'},
				{url: '/indexList', type: 'news_fashion', text: '时尚'}
      ],
      id: this.$route.params,
    };
  },
  components: {
    VTitle
  },
}
</script>
<style lang='stylus' scoped>
.top_menu_bar  
    background: #f4f5f6;
    position: fixed;
    z-index 1
    top: 40px;
    width: 100%;
    .top_menu_bar_ul
        overflow: hidden;
        overflow-x: auto;
        text-align: center;
        left: 0;
        font-size: 0;
        background: #f4f5f6;
        font-family: \\5FAE\8F6F\96C5\9ED1;
        white-space: nowrap;
        z-index: 999;
        .home_nav_item
            display: inline-block;
            height: 28px;
            line-height: 28px
            width: 40px;
            font-size: 14px;
            &.router-link-active
                color red
</style>