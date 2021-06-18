<template>
  <BigTopicComponent topic="ยินดีต้อนรับ" description="Lorem ipsum dolor sit amet, consectetur adipisicing elit. Asperiores, aspernatur"/>
  <ul class="z-10">
    <li>
      <router-link to="/">หน้าแรก</router-link>
    </li>
    <li>
      <router-link to="/about">เกี่ยวกับเรา</router-link>
    </li>
    <li>
      <router-link to="/about">บริการของเรา</router-link>
    </li>
    <li>
      <router-link to="/about">ผลงานของเรา</router-link>
    </li>
    <li>
      <router-link to="/about">ติดต่อเรา</router-link>
    </li>
  </ul>
  <router-view/>
  <footer class="py-12">
    <div class="space-y-10 md:space-y-0 md:grid md:grid-cols-2">
      <!-- left -->
      <div>
        <div class="text-center text-white">
          <h1 class="text-5xl mb-5">แผนที่</h1>
        </div>
        <div class="h-96 flex text-center text-white">
          <div class="m-auto">
            <div class="w-96 h-64 rounded-lg shadow-2xl bg-white"></div>
          </div>
        </div>
      </div>
      <!-- right -->
      <div>
        <div class="text-center text-white">
          <h1 class="text-5xl mb-5">ติดต่อเรา</h1>
        </div>
        <div class="h-96 flex text-center text-white">
          <div class="m-auto">
            <p>Lorem ipsum dolor sit amet sit amet</p>
            <p>Lorem ipsum dolor sit amet sit amet</p>
            <p>Lorem ipsum dolor sit amet sit amet</p>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import BigTopicComponent from './components/BigTopicComponent'

export default {
  components: {BigTopicComponent}
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

body {
  font-size: 28px;
}
</style>

<style scoped lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

body {
  font-size: 28px;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
  position: -webkit-sticky; /* Safari */
  position: sticky;
  top: 0;
  display: flex;
  justify-content: center;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #111;
}

footer {
  background-color: #333;
}

</style>
