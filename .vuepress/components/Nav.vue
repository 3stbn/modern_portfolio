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
        <li class="nav-item" :class="{ show: showMenu }">
          <a href="index.html" class="nav-link" >
            Home
          </a>
        </li>
        <li class="nav-item current" :class="{ show: showMenu }">
          <a href="about.html" class="nav-link">
            About Me
          </a>
        </li>
        <li class="nav-item" :class="{ show: showMenu }">
          <a href="work.html" class="nav-link">
            My Work
          </a>
        </li>
        <li class="nav-item" :class="{ show: showMenu }">
          <a href="contact.html" class="nav-link">
            How To Reach Me
          </a>
        </li>
      </ul>
    </nav>
  </header>    
</template>

<script>
export default {
  data () {
    return {
      showMenu: false
    }
  }
}
</script>
