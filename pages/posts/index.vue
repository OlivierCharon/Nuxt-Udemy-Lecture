<template>
  <div class="posts-page">
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'
export default {
  components: {
    PostList,
  },
  fetch(context) {
    return new Promise((resolve, reject) => {
      resolve({
        loadedPosts: [
          {
            id: '1',
            title: 'First post',
            previewText: 'This is our first post!',
            thumbnail:
              'https://tra.img.pmdstatic.net/fit/https.3A.2F.2Fi.2Einsider.2Ecom.2F5f2c4c6f988ee36b2d52d965/812x609/background-color/ffffff/quality/70/elon-musk-poem-tweets-gpt-3-openai-2020-8.jpg',
          },
          {
            id: '2',
            title: 'Second post',
            previewText: 'This is our second post!',
            thumbnail:
              'https://tra.img.pmdstatic.net/fit/https.3A.2F.2Fi.2Einsider.2Ecom.2F5f2c4c6f988ee36b2d52d965/812x609/background-color/ffffff/quality/70/elon-musk-poem-tweets-gpt-3-openai-2020-8.jpg',
          },
        ],
        // reject(new Error())
      })
        .then((data) => {
          context.store.commit('setPosts', data.loadedPosts)
        })
        .catch((e) => {
          context.error(e)
        })
    })
  },
  computed: {
    loadedPosts() {
      return this.$store.getters.loadedPosts
    },
  },
}
</script>

<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
