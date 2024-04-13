<template>
  <q-layout view="hhh lpr fff">
    <div class="gradient-bg">
      <q-header class="main-header">
        <div class="container row justify-between items-center">
          <img alt="cloit_logo" src="~assets/images/logo.svg" />

          <div class="row justify-between items-center d-none">
            <dropdown-menu />
            <div class="q-ml-xl">해외 개발자 활용 서비스</div>
          </div>

          <q-btn
            color="white"
            class="nav-btn d-none"
            label="문의하기"
            unelevated
          />
        </div>
      </q-header>

      <q-page-container>
        <div class="container">
          <router-view />
        </div>
      </q-page-container>
    </div>

    <q-footer class="footer">
      <div class="container">
        <div class="row">
          <div class="col-md-4 logo-sec">
            <img src="~assets/images/footer_logo.svg" alt="" />
            <p>
              우리는 국가의 장벽을 넘어 최고의 인재를 <br />
              매칭해드립니다.
            </p>

            <span>010-0000-0000</span>
            <span>aaaaa@naver.com</span>
          </div>
          <div class="col-md-8">
            <div class="info-boxes">
              <div v-for="(b, idx) in infoBoxes" :key="idx" class="info-box">
                <img :src="b.img" alt="" />

                <p>{{ b.title }}</p>

                <div class="action">
                  바로가기
                  <img src="~assets/icons/arrow-right.svg" alt="" />
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="row about-sec">
          <div class="col-md-4 q-mb-lg">
            <div class="about-right">
              <ul>
                <li class="title">상호명</li>
                <li>하이퍼하이어</li>
                <li>Hyperhire India Private Limited</li>
              </ul>

              <ul>
                <li class="title">대표 CEO</li>
                <li>김주현</li>
                <li>Juhyun Kim</li>
              </ul>
            </div>
          </div>
          <div class="col-md-8">
            <div class="about-left">
              <ul>
                <li class="title">사업자등록번호 CIN</li>
                <li>427-86-01187</li>
                <li>U74110DL2016PTC290812</li>
              </ul>

              <ul>
                <li class="title">주소 ADDRESS</li>
                <li>서울특별시 강남대로 479, 지하 1층 238호</li>
                <li>
                  D-138, Street number 11, Jagjeet Nagar, North East Delhi, New
                  Delhi, <br />
                  110053 India
                </li>
              </ul>
            </div>
          </div>
        </div>

        <div class="copyright">ⓒ 2023 Hyperhire</div>
      </div>
    </q-footer>
  </q-layout>
</template>

<script setup>
import DropdownMenu from "src/components/DropdownMenu.vue";

defineOptions({
  name: "MainLayout",
});

import code from "../assets/icons/code.svg";
import person from "../assets/icons/person.svg";
import kor from "../assets/icons/kor.svg";
import coge from "../assets/icons/coge.svg";

const infoBoxes = [
  {
    img: code,
    title: "해외 개발자 원격 채용",
  },
  {
    img: person,
    title: "외국인 원격 채용 (비개발)",
  },
  {
    img: kor,
    title: "한국어 가능 외국인 채용",
  },
  {
    img: coge,
    title: "해외 개발자 활용 서비스",
  },
];
</script>
