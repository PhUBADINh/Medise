<template>
    <div class="bg-gray-100 h-screen flex items-center justify-center bg-[url('./img/backgroundlogIn.jpg')] bg-cover">
      <div class="absolute inset-0 bg-black opacity-30"></div>
      <div class="relative z-10 bg-white shadow-lg min-h-[30rem] border-2 rounded-r-[100%] border-black rounded-2xl flex w-full max-w-4xl">
        <!-- Left side (Login) -->
        <div class="w-1/2 p-8 flex flex-col items-center">
          <h1 class="text-[1.8rem] font-bold mb-6">เข้าสู่ระบบ</h1>
          <form @submit.prevent="handleSubmit" class="space-y-4">
            <div>
              <label class="input input-bordered flex items-center gap-2">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="h-4 w-4 opacity-70">
                  <path
                    d="M2.5 3A1.5 1.5 0 0 0 1 4.5v.793c.026.009.051.02.076.032L7.674 8.51c.206.1.446.1.652 0l6.598-3.185A.755.755 0 0 1 15 5.293V4.5A1.5 1.5 0 0 0 13.5 3h-11Z" />
                  <path
                    d="M15 6.954 8.978 9.86a2.25 2.25 0 0 1-1.956 0L1 6.954V11.5A1.5 1.5 0 0 0 2.5 13h11a1.5 1.5 0 0 0 1.5-1.5V6.954Z" />
                </svg>
                <input type="email" id="email" v-model="email" class="grow" placeholder="Enter your Email" />
              </label>
            </div>
            <div>
              <label for="password" class="input input-bordered flex items-center gap-2 w-[22rem]">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="h-4 w-4 opacity-70">
                  <path fill-rule="evenodd" d="M14 6a4 4 0 0 1-4.899 3.899l-1.955 1.955a.5.5 0 0 1-.353.146H5v1.5a.5.5 0 0 1-.5.5h-2a.5.5 0 0 1-.5-.5v-2.293a.5.5 0 0 1 .146-.353l3.955-3.955A4 4 0 1 1 14 6Zm-4-2a.75.75 0 0 0 0 1.5.5.5 0 0 1 .5.5.75.75 0 0 0 1.5 0 2 2 0 0 0-2-2Z" clip-rule="evenodd" />
                </svg>
                <input type="password" id="password" v-model="password" class="grow" placeholder="Password" />
              </label>
            </div>
            <div class="flex justify-end my-5">
              <button>
                <p class="opacity-50">ลืมรหัสผ่านใช่หรือไม่ ?</p>
              </button>
            </div>
            <div class="flex justify-center">
              <button type="submit" :disabled="!isFormValid" class="text-[1.5rem] text-black bg-gradient-to-b from-[#00d6a8] to-[#00af89] h-[3.3rem] w-[17dvw] rounded-[50rem] hover:bg-gradient-to-b hover:from-[#00af89] hover:via-[#008c73] hover:to-[#006e5c] transition-all duration-300">เข้าสู่ระบบ</button>
            </div>
          </form>
          <div class="flex items-center">
            <div>
              <hr class="border-t-2 border-black w-[5rem] opacity-80 my-4">
            </div>
            <p class="mx-2">หรือ</p>
            <div>
              <hr class="border-t-2 border-black w-[5rem] opacity-80 my-4">
            </div>
          </div>
          <div class="mt-2">
            <div class="flex gap-7">
              <div>
                <img class="w-[3rem] h-[3rem]" src="../img/social1.png" alt="">
              </div>
              <div>
                <img class="w-[3rem] h-[3rem]" src="../img/social2.png" alt="">
              </div>
              <div>
                <img class="w-[3rem] h-[3rem]" src="../img/social3.png" alt="">
              </div>
            </div>
          </div>
        </div>
        <!-- Right side (Description) -->
        <div class="w-1/2 p-8 bg-[#10DBAC] text-white flex items-start border-[2px] border-black justify-center rounded-2xl">
          <div class="text-center flex flex-col justify-center mt-[-2.5rem]">
            <div class="flex justify-center flex-col">
              <h2 class="text-[2.7rem] w-[16rem] mt-[5rem] font-bold text-black">ไม่มีบัญชี</h2>
              <h1 class="text-[2rem] w-full ml-1 font-bold mb-2 text-black">ใช่หรือไม่ ?</h1>
            </div>
            <div>
              <p class="text-[1.5rem] text-black">กดสมัครเลยตอนนี้</p>
            </div>
            <div class="mt-4">
              <RouterLink :to="{name:'signup'}">
                <button class="bg-white h-[3.3rem] w-[17dvw] text-black text-[1.5rem] rounded-[50rem] hover:bg-[#656565] transition-all duration-300">สมัครการใช้งาน</button>
              </RouterLink>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        email: '',
        password: ''
      };
    },
    computed: {
      isFormValid() {
        // ตรวจสอบว่าช่องกรอกข้อมูลทุกช่องมีค่า
        return this.email !== '' && this.password !== '';
      }
    },
    methods: {
      handleSubmit() {
        if (this.isFormValid) {
          // เขียนฟังก์ชันการจัดการล็อกอินที่นี่ เช่น เรียก API
          this.$router.push('/')
          alert('เข้าสู่ระบบเรียบร้อย');
          
        }
      }
    }
  };
  </script>
  
  <style scoped>
  /* คุณสามารถปรับแต่ง CSS ตามที่ต้องการ */
  </style>
  