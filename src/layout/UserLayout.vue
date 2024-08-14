

<template>
    <div>
        <div class="app">
            <header
                class="navbar z-50 fixed top-0 left-0 w-screen h-24 bg-gradient-to-r from-[#4285F4] 0 to-[#264D8E] shadow-md transition-transform duration-100 ease-out p-6 px-14 flex justify-between items-center"
                :class="{ 'navbar--hidden translate-y-[-100%] shadow-none': !showNavbar }"
            >
                <RouterLink :to="{name : 'home'}" href="#" class="ml-24    "><img class="w-20 h-20" src="../img/iconLogo.png" alt="icon"></RouterLink>
                <nav class="flex items-center">
                    <RouterLink :to="{name:'home'}"   class="text-white ml-8 no-underline  hover:text-[#10DBAC] transition-colors duration-500 ease-in-out text-lg">หน้าหลัก</RouterLink>
                    <a href="#" class="text-white ml-8 no-underline  hover:text-[#10DBAC] transition-colors duration-500 ease-in-out text-lg">พบแพทย์</a>
                    <a href="#" class="text-white ml-8 no-underline  hover:text-[#10DBAC] transition-colors duration-500 ease-in-out text-lg">สินค้า</a>
                    <a href="#" class="text-white ml-8 no-underline  hover:text-[#10DBAC] transition-colors duration-500 ease-in-out text-lg">ตะกร้าสินค้า</a>
                    <a href="#" class="text-white ml-8 no-underline  hover:text-[#10DBAC] transition-colors duration-500 ease-in-out text-lg">ผลการรักษา</a>
                    <RouterLink :to="{name :'login'}"  class="ml-8 bg-white rounded-full"><img class="w-12 h-12" src="../img/person.png" alt=""></RouterLink>
                </nav>
            </header>
        </div>
        
        <slot></slot>
        <div>
            <footer class="footer min-w-min bg-[#3E296A] text-base-content p-10">
                <aside class="ml-[5rem]">
                    <img class="w-20 h-20 my-[-1rem]  ml-[8rem]" src="../img/iconLogo.png" alt="icon">
                    <p class="w-64 ml-[3rem]  my-[1rem] text-white">
                        เว็ปสำหรับการพบหมอออนไลน์ตั้งแต่พบแพทย์เพื่อให้คำปรึกษา สั่งยา เก็บประวัติและติดตามผล ให้บริการหลากหลายในด้านผิวทุกส่วนต่าง ๆ อาทิ ปรึกษาเรื่องสิว ชนิดผิวพรรณแต่ละประเภท รวมไปถึงผมและหนังศีรษะ
                    <br />
                    </p>
                </aside>
                <nav>
                    <h6 class="footer-title text-white">LINKS</h6>
                    <a class="link link-hover text-white">-หน้าหลัก</a>
                    <a class="link link-hover text-white">-พบแพทย์</a>
                    <a class="link link-hover text-white">-สินค้า</a>
                    <a class="link link-hover text-white">-ตะกร้าสินค้า</a>
                    <a class="link link-hover text-white">-ผลการรักษา</a>
                </nav>
                <nav>
                    <h6 class="footer-title text-white">CONTACT</h6>
                    <a class="link link-hover text-white">ติดต่อลงโฆษณา</a>
                    <a class="link link-hover text-white">โทร : 089 XXX XXXX</a>
                    <a class="link link-hover text-white">หรือ : 098 XXX XXXX</a>
                    <a class="link link-hover text-white">อีเมลล์ : XXXXXXXgmail.com</a>

                </nav>

                </footer>
        </div>
    </div>
</template>
<script>
import { RouterLink } from 'vue-router';
export default {
  data() {
    return {
      showNavbar: true,
      lastScrollPosition: 0
    };
  },
  mounted() {
    window.addEventListener('scroll', this.onScroll);
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.onScroll);
  },
  methods: {
    onScroll() {
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop;
      if (currentScrollPosition < 0) {
        return;
      }

      
      if (Math.abs(currentScrollPosition - this.lastScrollPosition) < 60) {
        return;
      }

      this.showNavbar = currentScrollPosition < this.lastScrollPosition;
      this.lastScrollPosition = currentScrollPosition;
    }
  }
};
</script>

<style>


  .navbar--hidden {

  }
</style>
