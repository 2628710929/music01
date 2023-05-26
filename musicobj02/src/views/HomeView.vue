<template>
  <div class="home">
    <top-nav></top-nav>
	<swiper-com></swiper-com>
	<icon-list></icon-list>
	<music-list></music-list>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import TopNav from '../components/TopNav.vue'
import MusicList from '../components/MusicList.vue'
import IconList from '../components/IconList.vue'
import SwiperCom from '../components/SwiperCom.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld,
	TopNav,
	MusicList,
	IconList,
	SwiperCom
  }
}
</script>

<style>
#d1{
  width: 3rem;
  height: 3rem;
  background: skyblue;
  font-size: 0.3rem;
}
</style>

