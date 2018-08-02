<template>
  <article>
    <Aside />
    <div class="r_box">
      <main>
        <router-link :to="{path: '/detail/'+item._id}" tag="div" v-for="item in postList" :key="item.id" >
          <PostItem :post="item" />
        </router-link>
      </main>
    </div>
  </article>
</template>

<script>
import Aside from "components/aside/Aside";
import PostItem from "components/post-item/Post-item";
import axios from "axios";
export default {
  name: "Home",
  data() {
    return {
      postList: [],
      postSize: 10,
      currentPage: 1
    };
  },
  mounted() {
    this.getPostList();
  },
  methods: {
    getPostList() {
      axios
        .get("/blog/post/postlist", {
          params: {
            postSize: this.postSize,
            currentPage: this.currentPage
          }
        })
        .then(res => {
          this.postList = res.data.postList;
        });
    }
  },
  components: {
    Aside,
    PostItem
  }
};
</script>
