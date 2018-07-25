<template>
  <article>
    <Aside />
    <div class="infosbox">
      <main>
        <div class="newsview">
          <h3 class="news_title">个人博客，属于我的小世界!</h3>
          <div class="bloginfo">
            <ul>
              <li class="author">作者：<a href="javascript:;">杨青</a></li>
              <li class="timer">时间：2018-5-13</li>
              <li class="view">4567人已阅读</li>
            </ul>
          </div>
          <div class="tags">
            <a href="/" target="_blank">个人博客</a> &nbsp; <a href="/" target="_blank">小世界</a>
          </div>
          <div class="news_con">
          </div>
        </div>
      </main>
    </div>
  </article>
</template>

<script>
import Aside from "components/aside/Aside";
import PostItem from "components/post-item/Post-item";
export default {
  name: "Detail",
  components: {
    Aside,
    PostItem
  }
};
</script>
