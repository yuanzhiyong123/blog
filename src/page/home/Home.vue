<template>
  <article>
    <Aside />
    <div class="r_box">
      <main>
        <Loading v-show="isLoaind" />
        <router-link :to="{path: '/detail/'+item._id}" tag="div" v-for="item in postList" :key="item.id" >
          <PostItem :post="item" />
        </router-link>
        <v-page class="pagenation" :setting="pageSet" @page-change="pageChange"></v-page>
      </main>
    </div>
  </article>
</template>

<script>
import Aside from "components/aside/Aside";
import PostItem from "components/post-item/Post-item";
import Loading from "components/loading/Loading";
import axios from "axios";
export default {
  name: "Home",
  data() {
    return {
      postList: [],
      postSize: 10,
      currentPage: 1,
      isLoaind: true,
      pageSet: {
        totalRow: 0,
        info: false,
        pageSizeMenu: [10]
      }
    };
  },
  mounted() {
    
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
          this.isLoaind = false;
          this.pageSet.totalRow = res.data.totalSize;
        });
    },
    pageChange(info) {
      this.currentPage = info.pageNumber;
      this.getPostList();
    }
  },
  components: {
    Aside,
    PostItem,
    Loading
  }
};
</script>
<style>
.pagenation li {
  padding: 0!important;
}
</style>
