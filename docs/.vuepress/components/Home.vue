<template>
  <main class="home">
    <header class="header">
      <a href="/" class="header-home"> Crystal </a>
      <div class="hero">
        <div
          v-for="(nav, index) in navList"
          :key="index"
          class="nav"
          @click="handleClickNav(nav)"
        >
          <div class="nav-item">{{ nav.text }}</div>
        </div>
      </div>
    </header>
    <div class="section-container">
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
.home {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;

  .section-container {
    background: url('/images/7.jpg') center no-repeat;
    background-size: cover;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #2c3c4a;
    color: #fff;
    padding: 0 20px;

    .header-home {
      color: #fff;
    }
  }

  .hero {
    width: 100%;
    height: 60px;
    display: flex;
    align-items: center;
    justify-content: flex-end;

    .nav {
      .nav-item {
        font-size: 16px;
        padding: 0 20px;
        cursor: pointer;

        &.active {
          color: #ccc;
        }
      }
    }
  }

  .footer {
    padding: 1rem;
    text-align: center;
    color: lighten($textColor, 25%);
    background: #2c3c4a;

    a {
      cursor: pointer;
      color: #fff;
    }
  }
}
</style>
