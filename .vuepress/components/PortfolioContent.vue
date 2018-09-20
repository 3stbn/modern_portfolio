<template>
    <div class="portfolio-page">
        <aside>
            <img :src="'../'+$page.frontmatter.img" alt="" width="100%">
            <a v-if="$page.frontmatter.extLink && $page.frontmatter.ref ":href="$page.frontmatter.extLink" target="_blank" class="btn-dark">
                <i :class="refIcon($page.frontmatter.ref)"></i> {{$page.frontmatter.ref }}
            </a>
        </aside>
        <div>
            <h2>{{$page.title}}</h2>
            <p class="port-desc">{{$page.frontmatter.description }}</p>
            <p v-for="tag in $page.frontmatter.tags" class="tags">{{tag}}</p>
        </div>        
    </div>
</template>

<script>
export default { 
  methods: { 
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