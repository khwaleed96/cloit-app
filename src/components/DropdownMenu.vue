<template>
  <div class="text-white row flex-center">
    <span class="cursor-pointer row flex-center">
      {{ selectedOpt }} <q-icon class="q-ml-xs" name="mdi-chevron-down" />
    </span>
    <q-menu v-model="showing" :offset="[0, 12]">
      <q-list style="min-width: 100px">
        <template v-for="(item, idx) in menuItems" :key="idx">
          <q-item clickable v-close-popup @click="onSelect(item)">
            <q-item-section class="text-weight-medium text-sm">{{
              item
            }}</q-item-section>
          </q-item>
          <q-separator color="#F2F4F7" v-if="idx === 2" />
        </template>
      </q-list>
    </q-menu>
  </div>
</template>

<script setup>
import { ref } from "vue";

defineOptions({
  name: "DropdownMenu",
});

let selectedOpt = ref("채용");
let showing = ref(false);

const menuItems = [
  "채용",
  "해외 개발자 원격 채용",
  "외국인 원격 채용 (비개발 직군)",
  "한국어 가능 외국인 채용",
];

const onSelect = (e) => (selectedOpt.value = e);
</script>
