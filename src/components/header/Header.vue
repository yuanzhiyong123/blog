<template>
  <header class="header-navigation" id="header">
    <nav>
      <div class="logo"><router-link to="/">相思雨博客</router-link></div>
      <h2 id="mnavh"><span class="navicon"></span></h2>
      <ul id="starlist">
        <li>
          <router-link to="/">网站首页</router-link>
        </li>
        <li>
          <!-- <router-link to="/detail" target="_blank">关于作者</router-link> -->
        </li>
      </ul>
  </nav>
</header>
</template>

<script>
export default {
  name: 'Home'
}
</script>
