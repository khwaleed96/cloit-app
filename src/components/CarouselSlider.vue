<template>
  <div class="carousel-slider">
    <swiper
      @swiper="onSwiper"
      :effect="'coverflow'"
      :grabCursor="true"
      :centeredSlides="true"
      slidesPerView="auto"
      :coverflowEffect="{
        rotate: 0,
        stretch: 139,
        depth: 120,
        modifier: 1,
        slideShadows: false,
      }"
      :loop="true"
      :modules="modules"
      class="mySwiper"
    >
      <swiper-slide
        class="profile-card"
        v-for="(item, idx) in profiles"
        :key="idx"
      >
        <div class="avatar">
          <div class="profile-image">
            <img :src="item.image" alt="img" srcset="" />
          </div>
          <img class="flag" :src="item.flag" alt="" />
        </div>
        <h3>{{ item.name }}</h3>
        <h6>{{ item.experience }}</h6>

        <div class="skills">
          <div v-for="(skill, idx) in item.skills" :key="idx">{{ skill }}</div>
        </div>
      </swiper-slide>
    </swiper>
    <q-icon
      class="prev-btn"
      @click="prev"
      name="mdi-chevron-left"
      size="xl"
      color="white"
    />
    <q-icon
      class="next-btn"
      @click="next"
      name="mdi-chevron-right"
      size="xl"
      color="white"
    />
  </div>
</template>

<script setup>
import { defineComponent } from "vue";

defineOptions({
  name: "CarouselSlider",
});

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

defineComponent({
  Swiper,
  SwiperSlide,
});

// Import Swiper styles
import "swiper/css";

import "swiper/css/effect-coverflow";

// import required modules
import { EffectCoverflow } from "swiper/modules";

const modules = [EffectCoverflow];

import profileImg from "../assets/images/profile.svg";
import flag from "../assets/icons/flag.svg";

const profiles = [
  {
    image: profileImg,
    flag: flag,
    name: "Abhishek Gupta",
    experience: "마케팅 · 2y+",
    skills: [
      "마케팅 콘텐츠 제작",
      "인스타그램 관리",
      "트위터 관리",
      "블로그 글 작성",
    ],
  },
  {
    image: profileImg,
    flag: flag,
    name: "Abhishek Gupta",
    experience: "마케팅 · 2y+",
    skills: [
      "마케팅 콘텐츠 제작",
      "인스타그램 관리",
      "트위터 관리",
      "블로그 글 작성",
    ],
  },
  {
    image: profileImg,
    flag: flag,
    name: "Abhishek Gupta",
    experience: "마케팅 · 2y+",
    skills: [
      "마케팅 콘텐츠 제작",
      "인스타그램 관리",
      "트위터 관리",
      "블로그 글 작성",
    ],
  },
  {
    image: profileImg,
    flag: flag,
    name: "Abhishek Gupta",
    experience: "마케팅 · 2y+",
    skills: [
      "마케팅 콘텐츠 제작",
      "인스타그램 관리",
      "트위터 관리",
      "블로그 글 작성",
    ],
  },
];

let eleSwiper = null;

const onSwiper = (swiper) => {
  eleSwiper = swiper;
};

const next = () => eleSwiper.slideNext();
const prev = () => eleSwiper.slidePrev();
</script>

<style lang="scss">
.carousel-slider {
  padding: 0px 56px;
  position: relative;

  .swiper {
    width: 100%;
  }
  .profile-card {
    width: 292px !important;
    background-color: #edfcff;
    padding: 36px;
    border-radius: 12px;
    box-shadow: 0px 0px 10px rgba($color: #000000, $alpha: 0.08);

    &.swiper-slide-active {
      background-color: #fff;
    }

    .avatar {
      position: relative;
      width: 120px;
      aspect-ratio: 1/1;
      margin: 0px auto 16px;

      .profile-image {
        width: 100%;
        height: 100%;
        overflow: hidden;
        img {
          width: 100%;
          object-fit: cover;
        }
      }

      .flag {
        position: absolute;
        bottom: 0px;
        right: 10px;
        z-index: 9;
      }
    }

    h3 {
      font-size: 24px;
      line-height: 36px !important;
      text-align: center;
      font-weight: 900 !important;
      color: #24252f;
      margin-bottom: 0px;
    }

    h6 {
      font-size: 16px;
      line-height: 24px !important;
      color: #4a77ff;
      font-weight: 900;
      text-align: center;
    }
    .skills {
      margin-top: 36px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      column-gap: 1px;
      row-gap: 4px;

      div {
        padding: 4px 10px 3px;
        border-radius: 6px;
        border: 1px solid #c1c5cf;
        font-weight: 900;
        font-size: 15px;
        line-height: 24px;
        color: #5e626f;
        display: inline-block;
      }
    }
  }

  .next-btn,
  .prev-btn {
    position: absolute;
    top: 50%;
    z-index: 99;
    transform: translateY(-50%);
    cursor: pointer;
  }

  .next-btn {
    right: 0px;
  }

  .prev-btn {
    left: 0px;
  }
}

@media screen and (max-width: 1200px) {
  .carousel-slider {
    max-width: 436px;
    margin: 0px auto;
    padding: 0px 25px;
    position: relative;

    .swiper {
      width: 100%;
    }
    .profile-card {
      width: 234px !important;
      background-color: #edfcff;
      padding: 36px 36px;

      &.swiper-slide-active {
        background-color: #fff;
      }

      .avatar {
        position: relative;
        width: 74px;
        aspect-ratio: 1/1;
        margin: 0px auto 16px;

        .flag {
          right: -10px;
        }
      }

      h3 {
        font-size: 18px;
        line-height: 27px !important;
      }

      h6 {
        font-size: 14px;
        line-height: 21px !important;
      }
      .skills {
        div {
          padding: 3px 9px 3px;
          font-size: 12px;
          line-height: 21px;
        }
      }
    }

    .next-btn {
      right: -10px;
    }

    .prev-btn {
      left: -10px;
    }
  }
}

@media screen and (max-width: 1023px) {
  .carousel-slider {
    max-width: 435px;
    margin: 0px auto;
  }
}
</style>
