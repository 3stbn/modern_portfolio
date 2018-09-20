---
title: Work
category: page
order: 3
---
<div>
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
        <a v-if="work.frontmatter.extLink && work.frontmatter.ref" :href="work.frontmatter.extLink" target="_blank" class="btn-dark">
            <i :class="refIcon(work.frontmatter.ref)"></i> {{work.frontmatter.ref}}
        </a>
    </div>    
</div>
</div>

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
    },
    refIcon(ref){
        if(/dribbble/ig.test(ref)){
            return 'fab fa-dribbble'
        }
        else if(/github/ig.test(ref)){
            return 'fab fa-github'
        }
        else if(/behance/ig.test(ref)){
            return 'fab fa-behance'
        }else {
            return ''
        }
    }
  }
}
</script>