<template>
  <div class="flex h-screen text-center rounded-3xl bg-gray-300">
    <div class="m-auto">
      <h1 class="text-6xl mb-5">{{topic}}</h1>
      <p>{{description}}</p>
      <p>{{description}}</p>
      <button class="w-44 mt-5 items-center justify-center rounded-lg bg-blue-500 text-white">เริ่ม</button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'BigTopic',
  props: {
    topic: String,
    description: String
  }
}
</script>
