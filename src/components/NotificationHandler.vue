<template>
  <div class="root">
    <ul>
      <li><button @click="isModal_1_Open = true">Open modal 1</button></li>
      <li><button @click="isModal_2_Open = true">Open modal 2</button></li>
      <li><button @click="isModal_3_Open = true">Open modal 3</button></li>
    </ul>

    <teleport to="body">
      <div class="modal" v-if="isModal_1_Open">
        <ModalContent_1
          @close="isModal_1_Open = false"
          title="isModal_1_Open"
          msg="isModal_1_Open"
        />
      </div>

      <div class="modal" v-if="isModal_2_Open">
        <ModalContent_2
          @close="isModal_2_Open = false"
          title="isModal_2_Open"
          msg="isModal_2_Open"
        />
      </div>

      <div class="modal" v-if="isModal_3_Open">
        <ModalContent_3
          @close="isModal_3_Open = false"
          title="isModal_3_Open"
          msg="isModal_3_Open"
        />
      </div>
    </teleport>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import ModalContent_1 from './ModalContent_1.vue'
import ModalContent_2 from './ModalContent_2.vue'
import ModalContent_3 from './ModalContent_3.vue'

const isModal_1_Open = ref(false)
const isModal_2_Open = ref(false)
const isModal_3_Open = ref(false)
</script>

<style>
.root {
  position: relative;
}

.modal {
  position: absolute;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.1);
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal > div {
  background-color: #fff;
  padding: 50px;
  border-radius: 10px;
}
</style>
