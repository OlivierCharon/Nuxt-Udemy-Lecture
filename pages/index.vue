<template>
  <div class="home-page">
    <section class="intro">
      <h1>Get the latest tech news!</h1>
    </section>
    <PostList :posts="loadedPosts" />
  </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'
export default {
  components: {
    PostList,
  },
  // data() {
  //   return {
  //     loadedPosts: [],
  //   }
  // },
  asyncData(context, callback) {
    callback(null, {
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
    })
  },
  created() {},
}
</script>

<style scoped>
.intro {
  height: 300px;
  position: relative;
  padding: 30px;
  box-sizing: border-box;
  background-position: center;
  background-size: cover;
  background-image: url('~assets/img/main-page-background.jpg');
}

.intro h1 {
  position: absolute;
  top: 10%;
  left: 5%;
  width: 90%;
  font-size: 1.5rem;
  color: black;
  background-color: rgb(211, 211, 211);
  padding: 10px;
  border-radius: 10px;
  text-align: center;
  box-sizing: border-box;
  border: 1px solid black;
}

@media (min-width: 768px) {
  .intro h1 {
    font-size: 2rem;
  }
}
</style>
