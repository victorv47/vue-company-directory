<script setup>
  import { faker } from '@faker-js/faker'

  const firstName = faker.name.firstName()
  const lastName = faker.name.lastName()
  const fullName = `${firstName} ${lastName}`

  const selectCard = () => {
   console.log(`${fullName} selected`)
  }
</script>

<template>
  <div class="card" @click="selectCard">
    <div class="card-image">
      <img :src="faker.internet.avatar()" alt="" srcset="" />
    </div>
    <div class="card-details">
      <p class="card-details-name">{{ fullName }}</p>
      <p class="card-details-job">{{ faker.name.jobTitle() }}, {{ faker.name.jobArea() }}</p>
      <p class="card-details-quote">"{{ faker.lorem.sentence() }}"</p>
    </div>
  </div>
</template>

<style scoped lang="postcss">
  .card {
    @apply cursor-pointer overflow-hidden rounded-md bg-slate-100 p-6 shadow-md transition-transform duration-100 hover:scale-105 hover:shadow-lg hover:shadow-slate-700;
    &-image {
      img {
        @apply mx-auto rounded-full object-contain;
      }
    }
    &-details {
      @apply flex flex-col gap-1 pt-6 text-center;
      &-name {
        @apply text-2xl font-thin text-blue-900;
      }
      &-job {
        @apply -mt-1 text-xs font-bold text-blue-400;
      }
      &-quote {
        @apply italic text-blue-900;
      }
    }
  }
</style>
