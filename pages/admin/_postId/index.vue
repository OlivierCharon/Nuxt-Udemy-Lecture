<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost" />
    </section>
  </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm'

export default {
  layout: 'admin',
  components: {
    AdminPostForm,
  },
  data() {
    return {
      loadedPost: {
        author: 'Olivier',
        title: 'Awesome post',
        content: 'What an amazing place holder!',
        thumbnailLink:
          'https://tra.img.pmdstatic.net/fit/https.3A.2F.2Fi.2Einsider.2Ecom.2F5f2c4c6f988ee36b2d52d965/812x609/background-color/ffffff/quality/70/elon-musk-poem-tweets-gpt-3-openai-2020-8.jpg',
      },
    }
  },
}
</script>

<style>
.update-form {
  width: 90%;
  margin: 20px auto;
}
@media (min-width: 768px) {
  .update-form {
    width: 500px;
  }

  img {
    width: 100%;
    justify-items: center;
    margin: 20px auto;
  }
}
</style>
