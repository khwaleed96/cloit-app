<template>
  <q-page>
    <div class="row q-mt-2xl">
      <!-- left side content -->
      <div class="col-12 col-md-6 info-section">
        <!-- label -->
        <transition appear enter-active-class="animated fadeIn fast delay-2s">
          <custom-label>
            <span style="color: #40e2e8; font-size: 18px"
              >풀타임, 파트타임</span
            >
          </custom-label>
        </transition>
        <transition
          appear
          enter-active-class="animated fadeInUp faster delay-1s"
        ></transition>
        <transition
          appear
          enter-active-class="animated fadeInUp faster delay-1s"
        >
          <h3 class="text-white text-weight-bolder text-h3 q-mt-md">
            최고의 실력을 가진 <br />
            외국인 인재를 찾고 계신가요?
          </h3>
        </transition>

        <transition
          appear
          enter-active-class="animated fadeInUp faster delay-1s"
        >
          <h5 class="text-h5 text-dim-white text-weight-bolder">
            법률 및 인사관리 부담없이 <br />
            1주일 이내에 원격으로 채용해보세요.
          </h5>
        </transition>
        <h6 class="text-white text-weight-bolder d-none">
          개발자가 필요하신가요?
        </h6>

        <transition appear enter-active-class="animated fadeInUp faster">
          <div
            class="row justify-between items-center no-wrap q-mt-2xl info-card-sec d-none"
          >
            <div class="info-card" v-for="(item, idx) in infoCards" :key="idx">
              <h6 class="text-white text-weight-bolder">{{ item.title }}</h6>
              <p class="text-dim-white">{{ item.description }}</p>
            </div>
          </div>
        </transition>
      </div>
      <!-- Right side content -->
      <div class="col-12 col-md-6">
        <div class="text-center q-mb-md">
          <!-- label -->
          <transition
            appear
            enter-active-class="animated fadeInUp faster delay-1s"
          >
            <custom-label class="stale big center">
              <dir class="row justify-between items-center q-gutter-sm">
                <img src="~assets/icons/dollar.svg" alt="" />
                <span style="color: #00c696; font-size: 18px">월 100만원</span>
              </dir>
            </custom-label>
          </transition>
        </div>
        <!-- carousel -->
        <carousel-slider class="q-mt-md" />
      </div>
    </div>
    <transition appear enter-active-class="animated fadeInUp faster delay-1s">
      <div class="slider d-none">
        <simple-slider />
      </div>
    </transition>
  </q-page>
</template>

<script setup>
defineOptions({
  name: "IndexPage",
});

import CustomLabel from "src/components/CustomLabel.vue";
import CarouselSlider from "src/components/CarouselSlider.vue";
import SimpleSlider from "src/components/SimpleSlider.vue";
// import { onMounted } from "vue";

const infoCards = [
  {
    title: "평균 월 120만원",
    description: "임금을 해당 국가를 기준으로 계산합니다.",
  },
  {
    title: "최대 3회 인력교체",
    description: "막상 채용해보니 맞지 않아도 걱정하지 마세요. ",
  },
  {
    title: "평균 3일, 최대 10일",
    description: "급하게 사람이 필요한 경우에도 빠른 채용이 가능합니다.",
  },
];
</script>
