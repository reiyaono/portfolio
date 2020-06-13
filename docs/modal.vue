<!DOCTYPE HTML>

<html lang="en-us">
<body style="margin: 0;">
  <div id="container" style="line-height: 0;">
    <header></header>
    <div style="line-height: 0;">
      <div style="position: relative; background-color: #000000;" @click="showModal = true">
        <img class="thumb" src="https://reiyaono.github.io/portfolio/images/photo/linkbal_thumbnail.jpg" @mouseover="linkbal = true" @mouseleave="toYouTube" style="width: 100%; height: 100%;"></img>
        <div class="imageText" v-if="linkbal">Instagram Advertising</div>
        <a href="https://www.youtube.com/watch?v=kvbr5yx80i4&t=0s" class="linkText" v-if="linkbal">Open on YouTube</a>
      </div>
      <img class="thumb" v-if="showModal" src="https://reiyaono.github.io/portfolio/images/photo/yourhands_thumbnail.jpg" style="width: 100%; height: 100%;"></img>
      <img class="thumb" src="https://reiyaono.github.io/portfolio/images/photo/quince_thumbnail.jpg" style="width: 100%; height: 100%;"></img>
      <img class="thumb" src="https://reiyaono.github.io/portfolio/images/photo/homies_thumbnail.jpg" style="width: 100%; height: 100%;"></img>
      <img class="thumb" src="https://reiyaono.github.io/portfolio/images/photo/aminas_thumbnail.jpg" style="width: 100%; height: 100%;"></img>
    </div>
    <div v-if="showModal" class="modal">モーーーーーーダル</div>
  </div>
</body>
<script src="https://cdn.jsdelivr.net/vue/latest/vue.js"></script>
<script type="text/javascript">
  var vm = new Vue({
    el: '#container',
    data: {
      linkbal: false,
      showModal: false
    },
    methods: {
      hoge () {
        console.log('ホゲ')
      },
      toYouTube () {
        window.open( 'https://www.youtube.com/watch?v=kvbr5yx80i4&t=0s' );
      }
    },
    computed: {
      availableFemale () {
        return this.femaleMax - this.femaleCounter
      },
      sum () {
        return this.maleCounter + this.femaleCounter
      },
      isExceedLimit () {
        return (this.maleCounter + this.femaleCounter) >= (this.femaleMax + this.maleMax)
      },
      isExceedMaleLimit () {
        return this.maleCounter > this.maleMax
      },
      isExceedFemaleLimit () {
        return this.femaleCounter > this.femaleMax
      }
    }
  })
</script>
<style type="text/css">
.thumb {
  background-color: #000000;
}
.thumb:hover {
  opacity: 0.45;
}
.imageText {
  position: absolute;
  top: 50%;
  right: 46%;
  font-size: 16px;
  color: #FFFFFF;
}
.linkText {
  position: absolute;
  top: 80%;
  right: 46%;
  font-size: 16px;
  color: #FFFFFF;
}
.modal {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  overflow-y: auto;
  visibility: hidden;
  opacity: 1;
  z-index: 100;
}
</style>
</html>
