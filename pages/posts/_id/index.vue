<template>
  <div class="single-post-page">
    <section>
      <h1 class="post-title">{{ loadedPost.title }}</h1>
      <div class="post-details">
        <div class="post-detail">
          Last update on {{ loadedPost.updatedDate }}
        </div>
        <div class="post-detail">Written by {{ loadedPost.author }}</div>
      </div>
      <p class="post-content">{{ loadedPost.previewText }}</p>
    </section>
    <section>
      <p class="post-feedback">
        Let me know what you think about the post: send a mail to
        <a
          href="mailto:olivier.charon@outlook.fr?subject=NuxtJS Amazing uDemy class"
          >olivier.charon@outlook.fr</a
        >
      </p>
    </section>
  </div>
</template>

<script>
export default {
  asyncData(context, callback) {
    callback(null, {
      loadedPost: {
        id: '1  ',
        title: 'First post (ID: ' + context.route.params.id + ')',
        author: 'Olivier CHARON',
        updatedDate: new Date(),
        previewText: 'This is our first post!',
        thumbnail:
          'https://tra.img.pmdstatic.net/fit/https.3A.2F.2Fi.2Einsider.2Ecom.2F5f2c4c6f988ee36b2d52d965/812x609/background-color/ffffff/quality/70/elon-musk-poem-tweets-gpt-3-openai-2020-8.jpg',
      },
    })
  },
}
</script>

<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>
