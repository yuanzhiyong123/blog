<template>
  <header class="header-navigation" id="header">
    <nav>
      <div class="logo"><a href="/">相思雨个人博客</a></div>
      <h2 id="mnavh"><span class="navicon"></span></h2>
      <ul id="starlist">
        <li>
          <router-link to="/">网站首页</router-link>
        </li>
        <li>
          <router-link to="/detail">关于作者</router-link>
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
