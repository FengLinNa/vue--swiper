<template>
  <div>
      <p class="curr">{{cur}}</p>
    <ul class="swiper-container">
      <div class="swiper-wrapper">
        <li v-for="(item,index) in posts" :key="index" class="swiper-slide">
          <img :src="item" alt>
        </li>
      </div>
    </ul>
  </div>
</template>
<script>
export default {
  props:["cur","change"],
  data() {
    return {
      posts: [
        "https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=1513222572,1724296872&fm=26&gp=0.jpg",
        "https://ss2.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=119991635,3338844579&fm=26gp=0.jpg",
        "https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3751132997,2377190187&fm=26&gp=0.jpg",
        "https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3667338627,4040384263&fm=26&gp=0.jpg",
        "https://ss1.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=1588770783,3837654158&fm=26&gp=0.jpg"
      ]
    };
  },
  mounted() {
      const that = this;
    this.swiper = new Swiper("ul", {
        on:{
            slideChange:function(cur){
                that.change(this.activeIndex)
            }
        }
    });
  },
  updated(){
      this.swiper.slideTo(this.cur)
  }
};
</script>
<style>
.curr{
    display: none;
}
</style>


