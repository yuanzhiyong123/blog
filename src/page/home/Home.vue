<template>
  <article>
    <Aside />
    <div class="r_box">
      <main>
        <router-link :to="{path: '/detail/'+item.id}" tag="div" v-for="item in postList" :key="item.id" >
          <PostItem :post="item" />
        </router-link>
      </main>
    </div>
  </article>
</template>

<script>
import Aside from "components/aside/Aside";
import PostItem from "components/post-item/Post-item";
import axios from 'axios';
export default {
  name: "Home",
  data() {
    return {
      postList: []
    };
  },
  mounted() {
    this.getPostList();
  },
  methods: {
    getPostList() {
      axios.get('/mock/post-list.json').then(res => {
        this.postList = res.data.postList;
      })
    }
  },
  components: {
    Aside,
    PostItem
  }
};
</script>
