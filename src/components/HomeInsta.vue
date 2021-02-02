<template>
  <div>
    <bodyHomeInsta :publishes="publishes"/>
  </div>
</template>

<script>
import axios from 'axios'
import BodyHomeInsta from './BodyHomeInsta.vue'
export default {
  components: { BodyHomeInsta },
  data() {
    return {
      publishes: [],
      activeUser: 'superman'
    }
  },
  async created () {
    this.publishes = await this.filterData()
      console.log(this.publishes)
  },
  methods: {
    async filterData() {
      const posts  = await axios.get('http://localhost:3001/posts')
      const comments  = await axios.get('http://localhost:3001/comments')
      const  likes  = await axios.get('http://localhost:3001/likes')

      const postsData = posts.data
      const commentsData = comments.data
      const likesData = likes.data

      const filterPublishes = postsData.map(post => {
        // o map é similitar a um for, ele passa em todas as possições de um ARRAY fazendo uma ação
        // nesse caso a ação que fizemos foi a de filtrar 
        const comment = commentsData.filter(comentario => comentario.postId == post.id);
        const like = likesData.filter(curtida => curtida.postId == post.id);

        // passa por todos as posições do post fazendo um filter nos comentarios e likes para pegar tudo relacionado ao id dos posts
        // depois retorna o post, os comentarios dele e os likes

        return {
          post: post,
          comments: comment,
          likes: like
        }
      })

      return filterPublishes;
    }
  }
}
</script>
<style>
[centro] {
  text-align: center;
  justify-content: center;
  align-items: center;
}
</style>