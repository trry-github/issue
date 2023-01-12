<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="wrapper">
    <nav>
      <RouterLink to="/"><button>Home</button></RouterLink>
      <RouterLink to="/about"><button>About</button></RouterLink>
    </nav>
  </div>
  <router-view v-slot="{ Component, route }">
    <transition name="main" mode="out-in" appear>
      <keep-alive include="about-view">
        <component :is="Component" :key="route.fullPath" />
      </keep-alive>
    </transition>
  </router-view>

</template>
<style scoped>
.wrapper {
  position: sticky;
  top: 0;
  text-align: center;
  background-color: #ddd;

}

.wrapper nav {
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

/* 主内容区动画 */
.main-enter-active {
  transition: 0.2s;
}

.main-leave-active {
  transition: 0.15s;
}

.main-enter-from {
  opacity: 0;
  margin-left: -10px;
}

.main-leave-to {
  opacity: 0;
  margin-left: 10px;
}
</style>
