---
title: Work
category: page
order: 3
---
<main>
<h1>
    My
    <span class="text-secondary">Work</span>
</h1>
<h2>
    Check out some of my projects...
</h2>
<div class="projects">
    <div class="item" v-for="work in works">
        <router-link tag="a" :to="work.path">
            <img :src = 'work.frontmatter.img' alt="Project">
        </router-link>
        <router-link tag="a" :to="work.path" class="btn-light">
            <i class="fas fa-eye"></i> {{work.frontmatter.title}} 
        </router-link>
        <a :href="work.frontmatter.extLink" target="_blank" class="btn-dark">
            <i class="fab fa-github"></i> Github
        </a>
    </div>    
</div>
</main>

<script>
export default {
  data () {
    return {
      works: []
    }
  },
  mounted() {
    this.works = this.filterWork();
  },
  methods: {
    filterWork() {
      let works = this.$site.pages
      let result = works.filter( work => work.frontmatter.category === 'portfolio')
      return result
    }
  }
}
</script>