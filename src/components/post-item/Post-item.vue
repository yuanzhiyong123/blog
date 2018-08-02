<template>
  <div>
    <li>
      <i><a href="/"><img :src="'http://localhost:777/'+post.image" alt="图片"></a></i>
        <h3><a href="/">{{post.title}}</a></h3>
        <p>{{post.descript}}</p>
      </li>
  </div>
</template>

<script>
export default {
  name: "PostItem",
  props: {
    post: {
      type: Object
    }
  }
}
</script>
