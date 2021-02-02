<template>
  <v-container>

    <v-container>
      informações
    </v-container>
    <v-divider ></v-divider>
    <v-container v-for="publishe in publishes" :key="publishe.post.id" class="mt-4 d-flex flex-column pa-4 elevation-2">
      <v-row>
        <!-- uma coluna que ocupa os 12 espaçoes -->
        <v-col md="6" sm="12">
          <img :src="publishe.post.picture" >
        </v-col>
        <v-col md="6" sm="12" class="pa-4">
          <v-row>
            <v-col cols="12" >
              <v-avatar size="40">
                <img :src="setUserProfilePicture(publishe.post.user)" />
              </v-avatar>
              <span class="nameUser black--text ml-2 font-weight-bold">
                {{publishe.post.user}}
              </span>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12">
              <span>
                {{publishe.post.title}}
              </span> 
            </v-col>
            <v-col cols="12" class="d-flex align-center justify-center">
              <fa-icon :icon="['fas', 'heart']"/> 
                <span class="mx-1">
                  {{publishe.likes.length}} 
                </span>
              <fa-icon :icon="['fas', 'comments']" class="ml-1"/> 
                <span class="mx-1">
                  {{publishe.comments.length}}                  
                </span>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
               <commentsHomeInsta :comments="publishe.comments"/>
            </v-col>
          </v-row>
        </v-col> 
      </v-row>
    </v-container>
  </v-container>
</template>

<script>
import CommentsHomeInsta from './CommentsHomeInsta.vue';
export default {
  components: { CommentsHomeInsta },
  props: ['publishes'],
  methods: {
    setUserProfilePicture(user) {
      switch(user) {
        case 'batman': 
          return 'https://i.pinimg.com/564x/36/60/58/366058cd421e6a981e50c6f800abbbd0.jpg';
        break;
        case 'superman': 
          return 'https://imgix-media.wbdndc.net/cms/filer_public_thumbnails/filer_public/c3/62/c362e8eb-8d38-4b07-9aea-fafadd1f8efc/superman-profile-2561b3-manofsteel1-cover-2-v1-600x600-marquee-thumb.jpg__600x600_q85_crop_subsampling-2_upscale.jpg'
        break;
        case 'wonderwoman': 
          return 'https://avatarfiles.alphacoders.com/167/thumb-1920-167527.jpg'
        break;
      }
    }
  }
}
</script>

<style>


img {
  width: 300px;
  height: 400px;
  margin: 5px;
}



/* .flex {
  margin-top: 12px;
  display: flex;
  align-items: center;
  margin-bottom: 10px;
  justify-content: center;
  border: 1px solid rgb(197, 195, 195);
  box-sizing: content-box ;
  height: inherit;
  width: 400px;
  border-radius: 10px;
  text-overflow: "…"
} */

.profilePic {
  
  bottom: 2.2rem;
  margin: 5px;
  width: 3rem;
  height: 3rem;
  border-radius: 1.5rem;
}uppercase

.postTitleClass {
  margin-top: 10px;
  font-size: 13px;
}

.nameUser {
  text-transform: capitalize;
}
</style>