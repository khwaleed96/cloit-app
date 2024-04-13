<template>
  <swiper
    :slidesPerView="'auto'"
    :spaceBetween="10"
    :freeMode="true"
    :modules="modules"
    :grabCursor="true"
    autoplay
    class="mySwiper"
  >
    <swiper-slide
      class="simple-slide"
      v-for="(item, idx) in SliderItems"
      :key="idx"
    >
      <div class="icon">
        <img :src="item.icon" alt="" />
      </div>
      <span>{{ item.title }}</span>
    </swiper-slide>
  </swiper>
</template>

<script setup>
import { defineComponent } from "vue";

defineOptions({
  name: "simpleSlider",
});

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

defineComponent({
  Swiper,
  SwiperSlide,
});

// Import Swiper styles
import "swiper/css";

import "swiper/css/free-mode";

// import required modules
import { FreeMode, autoplay } from "swiper/modules";

const modules = [FreeMode, autoplay];

import chartIcon from "../assets/icons/chart.svg";
import imgIcon from "../assets/icons/img.svg";
import cubeIcon from "../assets/icons/cube.svg";
import targetIcon from "../assets/icons/target.svg";
import phoneIcon from "../assets/icons/phone.svg";

const SliderItems = [
  {
    icon: chartIcon,
    title: "해외 마케팅",
  },
  {
    icon: imgIcon,
    title: "해외 마케팅",
  },
  {
    icon: cubeIcon,
    title: "캐드원(제도사)",
  },
  {
    icon: targetIcon,
    title: "해외 세일즈",
  },
  {
    icon: phoneIcon,
    title: "해외 CS",
  },
  {
    icon: imgIcon,
    title: "해외 마케팅",
  },
  {
    icon: cubeIcon,
    title: "캐드원(제도사)",
  },
  {
    icon: chartIcon,
    title: "해외 마케팅",
  },
];
</script>

<style lang="scss">
.simple-slide {
  width: 100%;
  max-width: 332px;
  padding: 16px;
  background-color: rgba(255, 255, 255, 0.2);
  display: flex;
  align-items: center;
  gap: 24px;
  border-radius: 12px;

  span {
    font-size: 24px;
    line-height: 36px;
    color: #fff;
  }
}

@media screen and (max-width: 1200px) {
  .simple-slide {
    max-width: 300px;
    img {
      max-width: 46px;
    }
    span {
      font-size: 18px;
      line-height: 32px;
    }
  }
}
</style>
