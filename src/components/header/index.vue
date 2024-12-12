<template>

</template>
<script>
  import { mapState } from 'vuex';
  import Bookmark from '../bookmark';
  import { Swiper, SwiperSlide } from "swiper/vue";
  import { Autoplay } from "swiper";
import "swiper/css";
  import Language from './language';
  import Notifications from './notifications.vue';
  import Mode from './mode';
  import Cart from './cart';
  import Profile from './profile';
  import Logo from './logo.vue';
  import SearchBar from './search';
  export default {
    components: {
      Bookmark,Language,Notifications,Mode,Cart,Profile,Logo,Swiper,SwiperSlide,SearchBar,
    },
    data() {
      return {
        bookmark: false,
      };
    },
    computed: {
      ...mapState({
        menuItems: (state) => state.menu.searchData,
        megamenuItems: (state) => state.menu.megamenu,
        searchOpen: (state) => state.menu.searchOpen,
      }),
    },
    methods: {
      search_open() {
        this.$store.state.menu.searchOpen = true;
      },
      bookmark_open() {
        this.bookmark = !this.bookmark;
      },
    },
    setup() {
    return {
      modules: [Autoplay],
    };
  },
  };
</script>
