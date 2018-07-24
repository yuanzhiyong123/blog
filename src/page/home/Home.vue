<template>
  <article>
    <Aside />
    <div class="r_box">
      <main>
        <PostItem v-for="item in 6" :key="item" />
      </main>
    </div>
  </article>
</template>

<script>
import Aside from "components/aside/Aside";
import PostItem from "components/post-item/Post-item";
export default {
  name: "Home",
  components: {
    Aside,
    PostItem
  }
};
</script>
