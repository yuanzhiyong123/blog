<template>
  <article>
    <Aside />
    <div class="r_box">
      <main>
        <router-link :to="{path: '/detail/'+item.id}" tag="div" v-for="item in postList" :key="item.id">
          <PostItem :post="item" />
        </router-link>
      </main>
    </div>
  </article>
</template>

<script>
import Aside from "components/aside/Aside";
import PostItem from "components/post-item/Post-item";
export default {
  name: "Home",
  data() {
    return {
      postList: [
        {
          id: "001",
          title: "你是什么人便会遇上什么人",
          content: "",
          author: "",
          descript:
            "有时就为了一句狠话，像心头一口毒钉，永远麻痺着亲密感情交流。恶言，真要慎出，平日多誠心爱语，乃最简易之佈施。",
          image: "../1.jpg",
          date: "12323",
          view_count: 20,
          type: "",
          comment: []
        },
        {
          id: "002",
          title: "你是什么人便会遇上什么人",
          content: "",
          author: "",
          descript:
            "有时就为了一句狠话，像心头一口毒钉，永远麻痺着亲密感情交流。恶言，真要慎出，平日多誠心爱语，乃最简易之佈施。",
          image: "../1.jpg",
          date: "12323",
          view_count: 20,
          type: "",
          comment: []
        },
        {
          id: "003",
          title: "你是什么人便会遇上什么人",
          content: "",
          author: "",
          descript:
            "有时就为了一句狠话，像心头一口毒钉，永远麻痺着亲密感情交流。恶言，真要慎出，平日多誠心爱语，乃最简易之佈施。",
          image: "../1.jpg",
          date: "12323",
          view_count: 20,
          type: "",
          comment: []
        }
      ]
    };
  },
  components: {
    Aside,
    PostItem
  }
};
</script>
