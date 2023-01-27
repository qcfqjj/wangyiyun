<template>
  <div>
    <TopNav />
    <SwpierTop />
    <iconList />
    <MusicList />
  </div>
</template>

<script>
// @ is an alias to /src
import TopNav from '@/components/home/TopNav.vue'
import SwpierTop from '@/components/SwpierTop.vue'
import iconList from '@/components/home/iconList.vue'
import MusicList from '@/components/home/MusicList.vue'
export default {
  name: 'HomeView',
  components: {
    TopNav,
    SwpierTop,
    iconList,
    MusicList
  }
}
</script>
