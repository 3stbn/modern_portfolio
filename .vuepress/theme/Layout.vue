<template>
  <div class="body" id="bg-img">
    <Nav></Nav>
    <main>
      <Content/>
    </main>    
    <Footer v-if="$page.title !== 'Home'"></Footer>
  </div>
  
</template>

<style lang="scss">
  * {
    margin: 0;
    padding: 0;
  }
    @import '../../scss/main.scss';
</style>
