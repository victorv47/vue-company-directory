<!-- eslint-disable prettier/prettier -->
<script setup>
  import { ref } from 'vue'
  const brand = ref("🏢 Victor's Company Directory")
</script>

<template>
  <nav>
    <div class="wrapper">
      <RouterLink :to="{ name: 'Home' }" class="brand">
        <span class="brand-title">{{ brand }}</span>
      </RouterLink>
      <div class="menu">
        <a href="#" class="menu-item">Departments</a>
        <a href="#" class="menu-item">Settings</a>
        <a href="#" class="menu-login">logout</a>
      </div>
    </div>
  </nav>
</template>

<style scoped lang="postcss">
  nav {
    @apply flex h-20 bg-blue-900 text-slate-100;
    .wrapper {
      @apply container mx-auto flex w-full items-center justify-between;
      .brand {
        &-title {
          @apply text-2xl font-bold text-blue-300;
        }
      }
      .menu {
        @apply flex gap-2;
        &-item {
          @apply rounded-md px-2 py-1 hover:bg-blue-400 hover:text-black;
        }
        &-login {
          @apply rounded-md bg-red-500 px-2 py-1 hover:bg-red-800;
        }
      }
    }
  }
</style>
