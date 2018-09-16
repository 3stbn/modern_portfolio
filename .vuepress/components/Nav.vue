<template>
<header>
    <div class="menu-btn" @click="showMenu = !showMenu " :class="{ close: showMenu }">
      <div class="btn-line"></div>
      <div class="btn-line"></div>
      <div class="btn-line"></div>
    </div>

    <nav class="menu" :class="{ show: showMenu }">
      <div class="menu-branding" :class="{ show: showMenu }">
        <div class="portrait"></div>
      </div>
      <ul class="menu-nav" :class="{ show: showMenu }">    
        <router-link tag="li" v-for="page in pages" :to="page.path" :key="page.key" class="nav-item" :class="{ show: showMenu }" @click.native="showMenu = !showMenu " >
            <a class="nav-link">{{page.title}}</a>
        </router-link>
      </ul>
    </nav>    
            
  </header>    
</template>

<script>
export default {
  data () {
    return {
      showMenu: false,
      pages: []
    }
  },
  mounted() {
    this.pages = this.filterPages();
  },
  methods: {
    filterPages() {
      let pages = this.$site.pages
      let result = pages.filter( page => page.frontmatter.category === 'page')
      return result.sort( (a,b) => a.frontmatter.order - b.frontmatter.order  )
    }
  }
}
</script>
