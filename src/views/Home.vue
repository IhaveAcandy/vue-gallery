<template>
  <div class="slideshow-container">
    <div class="mySlides fade">
      <img src="@/assets/img_snow_wide.jpg" style="width:100%">
    </div>
    <div class="mySlides fade">
      <img src="@/assets/img_snow_wide.jpg" style="width:100%">
    </div>
    <div class="mySlides fade">
      <img src="@/assets/img_snow_wide.jpg" style="width:100%">
    </div>
    <a class="prev" v-on:click="plusSlides(-1)">&#10094;</a>
    <a class="next" v-on:click="plusSlides(1)">&#10095;</a>
  </div>
  <div style="text-align:center">
    <span class="dot" v-on:click="currentSlide(1)"></span>
    <span class="dot" v-on:click="currentSlide(2)"></span>
    <span class="dot" v-on:click="currentSlide(3)"></span>
  </div>
  <InformationComponent index="1" topic="เกี่ยวกับเรา" description="Lorem ipsum dolor sit amet sit amet"/>
  <BigTopicComponent topic="บริการของเรา"/>
  <InformationComponent index="1" description="Lorem ipsum dolor sit amet sit amet"/>
  <InformationComponent index="2" description="Lorem ipsum dolor sit amet sit amet"/>
  <BigTopicComponent topic="ผลงานของเรา"/>
  <ul class="z-10">
    <li>
      <router-link to="/">ทั้งหมด</router-link>
    </li>
    <li>
      <router-link to="/about">ดีไซน์</router-link>
    </li>
    <li>
      <router-link to="/about">ประชาสัมพันธ์</router-link>
    </li>
    <li>
      <router-link to="/about">จัดงาน</router-link>
    </li>
  </ul>
  <div class="space-y-10 md:space-y-0 md:grid md:grid-cols-2 mt-3 mb-6">
    <PortfolioComponent/>
    <PortfolioComponent/>
    <PortfolioComponent/>
    <PortfolioComponent/>
  </div>
  <BigTopicComponent topic="ลูกค้าของเรา"/>
</template>

<script>
import { onMounted } from 'vue'
import BigTopicComponent from '@/components/BigTopicComponent.vue'
import InformationComponent from '@/components/InformationComponent.vue'
import PortfolioComponent from '@/components/PortfolioComponent.vue'

export default {
  setup() {
    let slideIndex = 1
    onMounted(async () => {
      showSlides(slideIndex)
    })

    const plusSlides = (n) => {
      showSlides(slideIndex += n)
    }

    const currentSlide = (n) => {
      showSlides(slideIndex = n)
    }

    const showSlides = (n) => {
      let i
      let slides = document.getElementsByClassName('mySlides')
      let dots = document.getElementsByClassName('dot')
      if (n > slides.length) {
        slideIndex = 1
      }
      if (n < 1) {
        slideIndex = slides.length
      }
      for (i = 0; i < slides.length; i++) {
        slides[i].style.display = 'none'
      }
      for (i = 0; i < dots.length; i++) {
        dots[i].className = dots[i].className.replace(' active', '')
      }
      slides[slideIndex - 1].style.display = 'block'
      dots[slideIndex - 1].className += ' active'
    }
    return {plusSlides, showSlides, currentSlide}
  },
  name: 'Home',
  components: {PortfolioComponent, InformationComponent, BigTopicComponent}
}
</script>

<style scoped>
* {
  box-sizing: border-box
}

body {
  font-family: Verdana, sans-serif;
  font-size: 28px;
  margin: 0
}

.mySlides {
  display: none
}

img {
  vertical-align: middle;
}

/* Slideshow container */
.slideshow-container {
  /*max-width: 100%;*/
  position: relative;
  margin: auto;
}

/* Next & previous buttons */
.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  padding: 16px;
  margin-top: -22px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
  user-select: none;
}

/* Position the "next button" to the right */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

/* On hover, add a black background color with a little bit see-through */
.prev:hover, .next:hover {
  background-color: rgba(0, 0, 0, 0.8);
}

/* The dots/bullets/indicators */
.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active, .dot:hover {
  background-color: #717171;
}

/* Fading animation */
.fade {
  -webkit-animation-name: fade;
  -webkit-animation-duration: 1.5s;
  animation-name: fade;
  animation-duration: 1.5s;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  position: -webkit-sticky; /* Safari */
  display: flex;
  justify-content: center;
}

li {
  float: left;
}

li a {
  display: block;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  border-bottom-width: 4px;
  border-bottom-color: white;
}

li a:hover {
  border-bottom-width: 4px;
  border-bottom-color: blue;
}

@-webkit-keyframes fade {
  from {
    opacity: .4
  }
  to {
    opacity: 1
  }
}

@keyframes fade {
  from {
    opacity: .4
  }
  to {
    opacity: 1
  }
}

/* On smaller screens, decrease text size */
@media only screen and (max-width: 300px) {
  .prev, .next, .text {
    font-size: 11px
  }
}
</style>
