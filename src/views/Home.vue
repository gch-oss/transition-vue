<template>
  <div class="home">
    <transition name="fade">
      <Toast v-if="showToast" />
    </transition>
    
    <Todos @badValue="triggerToast" />
  </div>
</template>

<!-- <script>
import { ref } from 'vue'
import Toast from '../components/Toast'
import Todos from '../components/Todos'

export default {
  components: { Toast, Todos },
  setup() {
    const showToast = ref(false)

    const triggerToast = () => {
      showToast.value = true;
      setTimeout(() => showToast.value = false, 3000)
    }

    return { showToast, triggerToast }
  }
}
</script> -->
<script setup>
//语法糖写法
import { ref } from 'vue'
import Toast from '../components/Toast'
import Todos from '../components/Todos'
const showToast = ref(false)

const triggerToast = () => {
  showToast.value = true;
  setTimeout(() => showToast.value = false, 2000)
}

</script>

<style>
/* .fade-enter-from {
  opacity: 0;
  transform: translateY(-60px);
} */
/* .fade-enter-to{
  opacity: 1;
  transform: translateY(0);
} */
.fade-enter-active {
  /* transition: all 0.3s ease; */
  animation: wobble 0.5s ease;
}
/* .fade-leave-from {
  opacity: 1;
  transform: translateY(0);
} */
/* .fade-leave-to {
  opacity: 0;
  transform: translateY(-60px);
} */
.fade-leave-active {
  /* transition: all 0.3s ease; */
  animation: wobble 0.5s ease;
}
@keyframes wobble {
  0% {transform: translateY(-60px);opacity: 0;}
  50% {transform: translateY(0);opacity: 1;}
  60% {transform: translateX(8px)}
  70% {transform: translateX(-8px)}
  80% {transform: translateX(4px)}
  90% {transform: translateX(-4px)}
  100% {transform: translateX(0)}
}
</style>