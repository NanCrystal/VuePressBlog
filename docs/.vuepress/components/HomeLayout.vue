<template>
  <main class="home">
    <header class="header">
      <a href="/" class="header-home"> N.Crystal✨ </a>
      <div class="hero">
        <div v-for="(nav, index) in navList" :key="index" class="nav" @click="handleClickNav(nav)">
          <div class="nav-item">{{ nav.text }}</div>
        </div>
      </div>
    </header>
    <div class="section_container">
      <!-- <img class="gif_style" src="../public/gifs/strong.gif" alt="" srcset="" /> -->
      <img class="gif_cycle" src="../public/gifs/cycle.gif" alt="" srcset="" />
      <div class="gif_button">
        <img class="gif_shaky" src="../public/gifs/shaky-button.gif" alt="" srcset="" />
        <span class="gif_button_text" >进入主页</span>
      </div>

      <!-- <img src="/images/7.jpg" /> -->
    </div>

    <div class="footer">
      <a href="https://beian.miit.gov.cn/" target="_blank">粤ICP备2021020229号</a>
    </div>
  </main>
</template>

<script>
import NavLink from "@theme/components/NavLink.vue";

export default {
  name: "Home",

  components: { NavLink },
  data() {
    return {
      navList: [
        { text: "主页", link: "/" }, // 根路径
        { text: "笔记", link: "/notes" }, // 外部链接
        { text: "日记", link: "https://google.com" }, // 外部链接
      ],
    };
    // return this.$page.frontmatter;
  },
  computed: {
    actionLink() {
      return {
        link: this.data.actionLink,
        text: this.data.actionText,
      };
    },
  },
  methods: {
    created() {
      console.log("data", this.data);
    },
    handleClickNav(item) {
      console.log("item", item);

      // window.location.href = url;
    },
  },
};
</script>

<style lang="stylus">
.home
  height 100vh
  width  100%
  display flex
  flex-direction column
  justify-content space-between

  .section_container
    // background url('/images/7.jpg') center no-repeat
    // background-size cover
    width 100%
    display flex
    flex-direction column
    justify-content flex-start
    align-items center
    .gif_style
      margin-top 60px
      width 380px
    .gif_cycle
      margin-top 60px
      width 540px
    .gif_button
      position relative
      cursor pointer
      .gif_shaky
        width 200px
      .gif_button_text
        position absolute
        top 50%
        left 50%
        transform translate(-50%,-50%)
        color #fff
        font-weight 600
        letter-spacing 4px
        // width 200px
 


  .header
    position fixed
    top 0
    right 0
    left 0
    display flex
    justify-content space-between
    align-items center
    border-bottom 1px solid rgba(60, 60, 67, .12)
    height 60px
    padding 0 20px
    .header-home
      color #2c3e50
    // display flex
    // width 100%
    // height 60px
    // justify-content space-between
    // align-items center
    // color #2c3e50
    // padding 0 20px



  .hero
    width 100%
    height 60px
    display flex
    align-items center
    justify-content flex-end
    .nav
      .nav-item
        font-size 16px
        padding 0 20px
        cursor pointer

        &.active
          color #ccc


  .footer
    padding 1rem
    text-align center
    
    // background #2c3c4a
    a
      cursor pointer
      color #2c3e50
</style>
