<template>
  <div class="post-list" v-if="posts.length > 0">
    <h3 class="post-list__title">Список постов:</h3>
    <transition-group name="post-list">
      <post-item
          v-for="post in posts"
          :post="post"
          :key="post.id"
          @remove="$emit('remove', post)"
      />
    </transition-group>
  </div>
  <h2 v-else class="post-list post-list_empty">
    Список постов пуст
  </h2>
</template>

<script>
import PostItem from "@/components/PostItem";
export default {
  components: {PostItem},
  props: {
    posts: {
      type: Array,
      required: true,
    }
  }
}
</script>

<style scoped>
.post-list {
  margin-top: 20px;
}
.post-list_empty {
  color: red;
}
.post-list__title {
  margin-bottom: 12px;
}
.post-list-item {
  display: inline-block;
  margin-right: 10px;
}
.post-list-enter-active,
.post-list-leave-active {
  transition: all .4s ease;
}
.post-list-enter-from,
.post-list-leave-to {
  opacity: 0;
  transform: translatex(140px);
}
.post-list-move {
  transition: transform .4s ease;
}
</style>