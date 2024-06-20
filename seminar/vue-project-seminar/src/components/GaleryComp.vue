<template>
  <div>
    <div class="active_img">
      <img :src="curentImgUrl" alt="">
    </div>
    <div class="desc_img">
      <img v-for="(img, index) in imgList" :key="index" :src="img.url" @click="chengeImgIndex(index)" alt="">
    </div>
</div>
</template>

<script>
export default {
  name: 'GaleryComp',

  data () {
    return {
      curentImgIndex: 0,
      imgList: [
        {
          url: 'https://i.pinimg.com/736x/7b/7b/b8/7b7bb891908ecef7c84d0c5cae5a9702--its-easy-animal-kingdom.jpg'
        },
        {
          url: 'https://www.sponsor-a-puppy.org.uk/wp-content/uploads/2019/04/Koala-Post.jpeg'
        },
        {
          url: 'https://img3.akspic.ru/previews/4/4/2/3/83244/83244-zhivaya_priroda-zivotnoe-morda-nazemnye_zhivotnye-kenguru-x350.jpg'
        },
        {
          url: 'https://vietint.net/wp-content/uploads/2018/10/au8.jpg'
        }
      ]
    }
  },

  computed: {
    curentImgUrl () {
      return this.imgList[this.curentImgIndex].url
    }
  },
  methods: {
    chengeImgIndex (index) {
      this.curentImgIndex = index
    }
  }
}
</script>

<style lang="scss" scoped>
    .desc_img img {
      width: 400px;
      height: 250px;
    }
    .active_img img {
      width: 100%;
    }
</style>
