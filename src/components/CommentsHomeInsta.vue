<template>
  <div>
    <v-row v-for="comment in comments" :key="comment.id" class="border-b">
      <v-col cols="12">
        <v-avatar size="24">
        <img :src="setUserProfilePicture(comment.user)">
        </v-avatar>
        <span class="font-weight-bold">
          {{comment.user}}
        </span>
      </v-col>
      <v-col cols="12">
        {{comment.comment}}
      </v-col>
      <v-divider light="true"></v-divider>
    </v-row>

  </div>
</template>

<script>
export default {
  props: ['comments'],
  methods: {
    setUserProfilePicture(user) {
      switch(user) {
        case 'batman': 
          return 'https://i.pinimg.com/564x/36/60/58/366058cd421e6a981e50c6f800abbbd0.jpg';
        break;
        case 'superman': 
          return 'https://imgix-media.wbdndc.net/cms/filer_public_thumbnails/filer_public/c3/62/c362e8eb-8d38-4b07-9aea-fafadd1f8efc/superman-profile-2561b3-manofsteel1-cover-2-v1-600x600-marquee-thumb.jpg__600x600_q85_crop_subsampling-2_upscale.jpg'
        break;
        case 'wonderWoman': 
          return 'https://avatarfiles.alphacoders.com/167/thumb-1920-167527.jpg'
        break;
        case 'captainAmerica':
          return 'https://64.media.tumblr.com/904630ac4fb6eefeb82012b96caa0bc8/tumblr_o6otc7tSOm1syt2szo1_1280.jpg'
        break;
        case 'thor':
          return 'https://media.wired.com/photos/59fb679f8e9fc3082a139c11/master/w_2560%2Cc_limit/Thor-MainArt.jpg'
        break;
        case 'greenLantern':
          return 'https://imgix-media.wbdndc.net/cms/filer_public/c9/64/c964ad0e-0789-4f2b-b578-0e9a91a487fe/greenlantern-profile-gledawntpb_cvr_recolor-v1-401x600-masthead.jpg'
        break;
        case 'blackWidow':
          return 'https://avatarfiles.alphacoders.com/215/thumb-1920-215726.jpg'
        break;
        case 'antman':
          return 'https://avatarfiles.alphacoders.com/755/thumb-1920-75566.jpg'
        break;
        case 'ironMan':
          return 'https://www.liveabout.com/thmb/xMwRnrIljoOXXlGUyN0oGgvRXNc=/768x0/filters:no_upscale():max_bytes(150000):strip_icc():format(webp)/FILM_ironman4-56a834265f9b58b7d0f184d1.jpg'
        break;
        case 'spiderMan':
          return 'https://avatarfiles.alphacoders.com/149/thumb-149117.jpg'
        break;
        case 'aquaman':
          return 'https://avatarfiles.alphacoders.com/167/thumb-1920-167551.jpg'
        break;
        case 'captainMarvel':
          return 'https://avatarfiles.alphacoders.com/176/thumb-1920-176479.jpg'
        break;
        default: 
          return 'https://i.stack.imgur.com/l60Hf.png'
        break;
          
     }
    }
  }
}

</script>

<style>

.border-b {
  border-bottom: 1px solid #EAEAEA;
}

</style>