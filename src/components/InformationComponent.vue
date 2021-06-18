<template>
  <div v-if="index % 2 != 0" class="space-y-10 md:space-y-0 md:grid md:grid-cols-2 my-4">
    <!-- left -->
    <div class="h-screen">
      <img class="h-screen rounded-3xl mx-5" src="@/assets/img_snow_wide.jpg" style="width:100%">
    </div>
    <!-- right -->
    <div class="h-screen flex text-center">
      <div class="m-auto">
        <h1 class="text-5xl mb-5">{{ topic }}</h1>
        <p>{{ description }}</p>
        <p>{{ description }}</p>
        <p>{{ description }}</p>
        <p>{{ description }}</p>
        <p>{{ description }}</p>
        <div class="grid justify-items-end">
          <button class="w-40 mt-5 justify-center rounded-lg bg-blue-500 text-white">เพิ่มเติม</button>
        </div>
      </div>
    </div>
  </div>
  <div v-else class="space-y-10 md:space-y-0 md:grid md:grid-cols-2 my-4">
    <!-- left -->
    <div class="h-screen flex text-center">
      <div class="m-auto">
        <h1 class="text-5xl mb-5">{{ topic }}</h1>
        <p>{{ description }}</p>
        <p>{{ description }}</p>
        <p>{{ description }}</p>
        <p>{{ description }}</p>
        <p>{{ description }}</p>
        <div class="grid justify-items-end">
          <button class="w-40 mt-5 justify-center rounded-lg bg-blue-500 text-white">เพิ่มเติม</button>
        </div>
      </div>
    </div>
    <!-- right -->
    <div class="h-screen">
      <img class="h-screen rounded-3xl mx-5" src="@/assets/img_snow_wide.jpg" style="width:100%">
    </div>
  </div>
</template>
<script>
export default {
  name: 'InformationComponent',
  props: {
    index: String,
    topic: String,
    description: String
  }
}
</script>
