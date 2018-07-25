<template>
  <article>
    <Aside />
    <div class="infosbox">
      <main>
        <div class="newsview">
          <h3 class="news_title">{{postDetail.title}}</h3>
          <div class="bloginfo">
            <ul>
              <li class="author">作者：<a href="javascript:;">{{postDetail.author}}</a></li>
              <li class="timer">时间：{{postDetail.date}}</li>
              <li class="view">{{postDetail.view_count}}人已阅读</li>
            </ul>
          </div>
          <div class="tags">
            <a href="/" target="_blank">{{postDetail.type}}</a> &nbsp; <a href="/" target="_blank">小世界</a>
          </div>
          <div class="news_con" v-html="postDetail.content"></div>
        </div>
      </main>
    </div>
  </article>
</template>

<script>
import axios from 'axios'
import Aside from "components/aside/Aside";
import PostItem from "components/post-item/Post-item";
export default {
  name: "Detail",
  data() {
    return {
      postDetail: {}
    }
  },
  mounted() {
    this.getDetail();
  },
  methods: {
    getDetail() {
      const postid = this.$route.params.id;
      axios.get('/mock/post-list.json?postid=' + postid).then(res => {
        this.postDetail = res.data.postList[0];
      });
    }
  },
  components: {
    Aside,
    PostItem
  }
};
</script>
